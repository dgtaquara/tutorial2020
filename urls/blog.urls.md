# blog.urls

Agora crie um novo arquivo vazio dentro do diretório `blog` chamado `urls.py`, feito isso adicione as duas linhas abaixo:

```text
from django.urls import path
from blog import views
```

Aqui nós estamos apenas importando métodos do Django e todos os nossos views do aplicativo blog \(ainda não temos nenhuma, mas teremos em um minuto!\)

Depois disso, nós podemos adicionar nossa primeira URL padrão logo abaixo das duas linhas citadas acima:

```text
urlpatterns = [
    path('', views.post_list)
]
```

Como você pode ver, estamos agora atribuindo uma `view` chamada `post_list` para a URL `''`. Este padrão irá mostrar ao Django que `views.post_list` é o lugar certo para ir, se alguém entra na sua página inicial.

Tudo certo? Se você tentar rodar o projeto agora, não vai conseguir.

![Tela de erro na aplica&#xE7;&#xE3;o](../.gitbook/assets/image%20%2821%29.png)

Antes disso, precisamos criar o `post_list`. Isto é como chamamos o nosso view! Isso significa que está tudo no lugar, só não criamos nossa view ainda. Não se preocupe, nós chegaremos lá.

> Se você quer saber mais sobre Django URLs, veja a documentação oficial: [https://docs.djangoproject.com/en/3.0/topics/http/urls/](https://docs.djangoproject.com/en/3.0/topics/http/urls/)

