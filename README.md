# Índice

[Pyhon](#python) <br>
[Ambiente virtual](#ambiente-virtual) <br>
[Django](#django) <br>
[Django admin](#django-admin) <br>
[App](#app) <br>

Esse tutorial foi criado no sistema operacional **_Linux_**. Alguns comandos podem ser diferentes se você estiver utilizando _Windows_ ou _Mac_.

# Python
[&uarr;](#índice)

Se você ainda não tem o Python instalado no seu computador pode fazer o download [aqui](https://www.python.org/downloads/), ou se preferir pode usar a distribuição [Anaconda](https://www.anaconda.com/products/individual).

# Ambiente virtual
[&uarr;](#índice)

Vamos criar a pasta do nosso projeto e criar um ambiente virtual. Em primeiro lugar, no seu terminal, instale o _virtualenv_:

```
pip install virtualenv
```

Crie e acesse a pasta do projeto. Escolha o nome que preferir, para esse tutorial escolhemos o nome `djangotutorial`:

```
mkdir djangotutorial
cd djangotutorial
```

Em seguida crie o ambiente virtual (dentro da pasta do projeto). Novamente escolha o nome que preferir, aqui vamos usar _venv_:

```
python -m venv venv
```

Se optar por criar uma pasta oculta basta adicionar _._ antes do nome da pasta, por exemplo _.venv_.

Teremos a seguinte estrutura (no _Windows_ e _Mac_ essa estrutura pode ser um pouco diferente):

```
djangotutorial/
└── venv
    ├── bin
    ├── include
    ├── lib
    ├── lib64 -> lib
    └── pyvenv.cfg
```

Para ativar o ambiente virtual basta usar o comando:

```
source venv/bin/activate
```

E para desativar:

```
deactivate
```

Se estiver usando o _Anaconda_ os comandos para criar, ativar e desativar o ambiente virtual são:

```
conda create -n venv python=3.7 anaconda
source activate venv
deactivate venv

```

Você pode trocar o nome _venv_ e a versão do Python que está utilizando.

Ao ativar o ambiente virtual você verá o nome que escolheu entre parênteses no início da linha de comando, por exemplo:

```
(venv) marcia@nt-marcia:~/djangotutorial$
```

# Django
[&uarr;](#índice)

Antes de iniciar as intalações do nosso ambiente virtual vamos atualizar o `pip`:

```
python -m pip install --upgrade pip
```

Agora vamos instalar o _Django_ no nosso ambiente virtual, certifique-se de que ele está ativado.

```
pip install django
```

Esse comando irá instalar a versão mais recente do _Django_ mas você pode especificar uma versão usando o comando `pip install Django==2.2.1` por exemplo.

Usando o _Anaconda_ o comando é:

```
conda install -c anaconda django
```

Agora que temos o _Django_ instalado, podemos começar nosso projeto com o comando:

```
django-admin startproject djangotutorial
```

Recomendo usar o mesmo nome da pasta criada anteriormente, mas voĉe pode escolher outro nome. Teremos uma estrutura assim:

```
├── djangotutorial
│   ├── djangotutorial
│   └── manage.py
└── venv
    ├── bin
    ├── include
    ├── lib
    ├── lib64 -> lib
    └── pyvenv.cfg
```

Vamos entrar na pasta `djangotutorial` onde está o arquivo `manage.py` e executar o comando:

```
cd djangotutorial
python manage.py runserver
```

_Voilà!_ Temos nosso primeiro projeto no ar [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

<p align="center">
    <img src="https://user-images.githubusercontent.com/75334161/110520756-aa6ff300-80ed-11eb-9e5b-ed0d93551b7d.png" width="700">
</p>

Ao usar o comando `runserver` pela primeira vez você verá uma mensagem similar a essa:

```
You have 18 unapplied migration(s). Your project may not work properly until you
apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```

Precisamos executar o comando `migrate` que fará alterações no banco de dados. Toda vez que criarmos novos tabelas no banco de dados precisamos executar o comando `makemigrations` e `migrate`. Mas por enquanto iremos apenas executar as alterações iniciais da configuração do Django.

```
python manage.py migrate
```

O resultado será algo assim:

```
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying auth.0010_alter_group_name_max_length... OK
  Applying auth.0011_update_proxy_permissions... OK
  Applying auth.0012_alter_user_first_name_max_length... OK
  Applying sessions.0001_initial... OK
```

> **Dica**: Você pode abrir uma nova aba ou uma nava janela do terminal para continuar usando os comandos do _Django_ sem ter que interromper o servidor.
> 

# Django admin
[&uarr;](#índice)

Para acessar o [`Django-admin`](http://127.0.0.1:8000/admin/) precisamos criar um `superuser`:

```
python manage.py createsuperuser
```

> **Atenção**: Só é possível criar o `superuser` após a execução do comando `migrate`
> 

Você deverá preencher _username_, _e-mail_ e _password_

Pronto. Agora você pode acessar o [`Django-admin`](http://127.0.0.1:8000/admin/). Você verá essa tela:

<p align="center">
    <img src="https://user-images.githubusercontent.com/75334161/110528210-a72d3500-80f6-11eb-8cca-fdf933dbae5b.png" width="700">
</p>

# App
[&uarr;](#índice)

```
python manage.py startapp myapp
```

