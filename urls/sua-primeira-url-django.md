# Sua primeira URL Django

É hora de criar nossa primeira URL! Queremos que nossa página inicial do nosso blog e exibir uma lista de posts.

Também queremos manter o arquivo de `meusite/urls.py` limpo, aí nós importaremos URLs da nossa aplicação blog para o arquivo principal meusite`/urls.py`.

Vá em frente e adicione uma linha que vai importar `blog.urls` para a url principal \(`''`\).

O seu arquivo `meusite/urls.py` deve agora se parecer com isto \(não esqueça de importar o `include` também!\):

```text
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('blog.urls'))
]
```

O Django agora irá redirecionar tudo o que entra na sua página inicial para `blog.urls` e procurar por novas instruções lá.

