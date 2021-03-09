# Índice

[Pyhon](#python)

[Ambiente virtual](#amiente-virtual)

[Django](#django)

Esse tutorial foi criado no sistema operacional Linux. Alguns comando podem ser diferentes se você estivr utilizando Windows ou Mac.

# Python

Se você ainda não tem o Python instalado no seu computador, você pode fazer o download [aqui](https://www.python.org/downloads/).

# Ambiente virtual

Vamos criar a pasta do nosso projeto e criar um ambiente virtual. Em primeiro lugar, no seu terminal instale o _virtualenv_:

`pip install virtualenv`

Crie e acesse a pasta do projeto. Escolha o nome que preferir, para esse tutorial escolhemos o nome ´djangotutorial´:

```
mkdir djangotutorial
cd djangotutorial
```

Em seguida crie o ambiente virtual (dentro da pasta do projeto). Novamente escolha o nome que preferir, aqui vamos usar _venv_:

`python -m venv venv`

Teremos a seguinte estrutura:

```
djangotutorial/
└── venv
    ├── bin
    ├── include
    ├── lib
    └── lib64 -> lib
```

Para ativar o ambiente virtual basta usar o comando:

`source venv/bin/activate`

E para desativar:

`deactivate`

# Django
