# Criando uma aplicação

Para manter tudo arrumado vamos criar um aplicativo separado dentro do nosso projeto. É muito bom ter tudo organizado desde o início. 

Digite o comando `pwd` seguido de um `Enter` para garantir que você está na pasta correta \(dg-worspace\).

```text
$ pwd
/workspace/dg-workspace
```

Então, para criar um aplicativo precisamos executar o seguinte comando no console:

```text
python3 manage.py startapp blog
```

Você vai notar que um novo diretório blog é criado e que ele agora contém um número de arquivos. Nossos diretórios e arquivos no nosso projeto devem se parecer com este:

![Menu lateral de arquivos do Gitpod](../../.gitbook/assets/image%20%285%29.png)

Depois de criar um aplicativo também precisamos dizer ao Django que deve usá-lo. Fazemos isso no arquivo `meusite/settings.py`.

Precisamos encontrar o `INSTALLED_APPS` e adicionar uma linha com `'blog'`, logo acima do `)`. É assim que a configuração deve ficar \(não esqueça da vírgula\):

```text
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog',
)
```

Salve o arquivo e vamos em frente!



