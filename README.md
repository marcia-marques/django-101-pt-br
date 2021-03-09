# Índice

[Pyhon](#python) <br>
[Ambiente virtual](#ambiente-virtual) <br>
[Django](#django) <br>

Esse tutorial foi criado no sistema operacional **_Linux_**. Alguns comandos podem ser diferentes se você estiver utilizando _Windows_ ou _Mac_.

# Python [&uarr;](#índice)

Se você ainda não tem o Python instalado no seu computador pode fazer o download [aqui](https://www.python.org/downloads/), ou se preferir pode usar a distribuição [Anaconda](https://www.anaconda.com/products/individual).

# Ambiente virtual [&uarr;](#índice)

Vamos criar a pasta do nosso projeto e criar um ambiente virtual. Em primeiro lugar, no seu terminal, instale o _virtualenv_:

```
pip install virtualenv
```

Crie e acesse a pasta do projeto. Escolha o nome que preferir, para esse tutorial escolhemos o nome ´djangotutorial´:

```
mkdir djangotutorial
cd djangotutorial
```

Em seguida crie o ambiente virtual (dentro da pasta do projeto). Novamente escolha o nome que preferir, aqui vamos usar _venv_:

```
python -m venv venv
```

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

# Django [&uarr;](#índice)

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
    <img src="https://user-images.githubusercontent.com/75334161/110520756-aa6ff300-80ed-11eb-9e5b-ed0d93551b7d.png" width="350">
</p>
