# URLs e Views

## URL

Vamos abrir o arquivo `blog/urls.py` e escrever:

```python
path(r'^post/new/$', views.post_new, name='post_new'),
```

O código final deve se parecer com isso:

```python
from django.urls import path
from blog import views

urlpatterns = [
    path('', views.post_list),
    path(r'^post/(?P<pk>[0-9]+)/$', views.post_detail, name='post_detail'),
    path(r'^post/new/$', views.post_new, name='post_new'),
]
```

Após atualizar o site, nós veremos um `AttributeError`, já que nós não temos a view `post_new` implementada. Vamos adicioná-la agora.

## A view post\_new

Hora de abrir o arquivo `blog/views.py` e adicionar as linhas seguintes com o resto das linhas `from`:

```python
from .forms import PostForm
```

e então a nossa _view_:

```python
def post_new(request):
    form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Para criar um novo formulário `Post`, nós devemos chamar `PostForm()` e passá-lo para o template. Nós voltaremos para esta _view_, mas por agora, vamos criar rapidamente um template para o formulário.

