# Administração

Para adicionar, editar e remover postagens que nós criamos usaremos o Django admin. Vamos abrir o arquivo `blog/admin.py` e substituir seu conteúdo por:

```text
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Após alterar, salve o arquivo.

Como você pode ver, nós importamos \(registramos, incluímos\) o modelo Post definido no capítulo anterior. Para tornar nosso modelo visível na página de administração, nós o registramos com: `admin.site.register(Post)`.

OK, hora de olhar para o nosso modelo de Post. Você esteve com o Preview de um site, com uma nave voando, aberto desde que iniciou o projeto, certo? Expanda-o clicando no ícone com uma seta no canto superior direito, sinalizado  a seguir em vermelho:

![Barra de URL do preview do site](.gitbook/assets/image%20%2834%29.png)

Você abrirá seu site em uma nova aba no navegador que está usando. Escreva na URL `/admin`. No nosso exemplo vai ficar algo como: [https://8080-d5ad6e0f-6fc8-4f86-87ca-845af32a8c20.ws-us02.gitpod.io/admin/login/?next=/admin/](https://8080-d5ad6e0f-6fc8-4f86-87ca-845af32a8c20.ws-us02.gitpod.io/admin/login/?next=/admin/) Mas não se assuste! Você verá uma página de login assim:

![](.gitbook/assets/image%20%2838%29.png)

Para fazer login, você precisa criar um _superusuário \(superuser\)_ - uma conta de usuário que pode controlar tudo no site. Volte à linha de comando, digite:

```text
$ python manage.py createsuperuser
```

e aperte `Enter`.

Será necessário preencher informações de usuário, e-mail e senha. Você pode colocar tudo como 'admin' mesmo, como segue abaixo:

```text
gitpod /workspace/dg-workspace $ python manage.py createsuperuser
Username (leave blank to use 'gitpod'): admin
Email address: admin@admin.com
Password: 
Password (again): 
The password is too similar to the username.
This password is too short. It must contain at least 8 characters.
This password is too common.
Bypass password validation and create user anyway? [y/N]: y
Superuser created successfully.
```

Não se preocupe que você não pode ver a senha que você está digitando - é assim que deve ser. Só digitá-la e pressione `Enter` para continuar. Se aparecer uma linha com uma pergunta e com opções de \[y/N\], digite y e pressione `Enter` novamente.

Volte para a o navegador e faça login com as credenciais de superuser que você escolheu, você deve visualizar o painel de controle do Django admin.

![Tela de usu&#xE1;rio administrador do Django](.gitbook/assets/image%20%2830%29.png)

Vá para a opção **Posts** e experimente um pouco com elas. Adicione cinco ou seis postagens. Não se preocupe com o conteúdo - você pode copiar e colar algum texto deste tutorial para o conteúdo para economizar tempo :\).

Certifique-se que pelo menos duas ou três postagens \(mas não todas\) tenham a data de publicação \(_published date_\) definida. Isso será útil depois.

![Tela de adicionar postagens no Django](.gitbook/assets/image%20%286%29.png)

Se você quiser saber mais sobre o Django admin, você pode conferir a documentação oficial: [https://docs.djangoproject.com/en/3.0/ref/contrib/admin/](https://docs.djangoproject.com/en/3.0/ref/contrib/admin/)

Este é provavelmente um bom momento para tomar um café \(ou chocolate\) e/ou algo para comer para repor as energias. Você criou seu primeiro modelo de Django - você merece um pouco de descanso!

