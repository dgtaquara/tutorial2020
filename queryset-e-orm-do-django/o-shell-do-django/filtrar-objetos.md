# Filtrar objetos

Uma grande parte de QuerySets é a habilidade de filtrá-los. Digamos que queremos encontrar todos as postagens escritas pelo usuário `admin`. Nós usaremos o `filter` em vez de all em `Post.objects.all()`. Entre parênteses indicamos que as condições precisam ser atendidas por um postagem de blog para acabar em nosso queryset. Em nosso caso é `author` que é igual a `eu`. A maneira de escrever isso no Django é: `author=eu`. Agora o nosso trecho de código parece com este:

```text
In [10]: Post.objects.filter(author=eu)                                           
Out[10]: <QuerySet [<Post: Postagem 1>, <Post: Postagem 2>, <Post: Título de exemplo>]>
```

Ou talvez nós queremos ver todos os posts que contenham a palavra 'título' no campo de `title`?

```text
In [11]: Post.objects.filter(title__contains='título')                            
Out[11]: <QuerySet [<Post: Título de exemplo>]>
```

> Nota: Existem dois caracteres de sublinhado `(_)` entre o `title` e `contains`. Django ORM usa esta sintaxe para separar nomes de campo \("title"\) e operações ou filtros \("contains"\). Se você usar apenas um sublinhado, você obterá um erro como "_FieldError: Cannot resolve keyword title\_contains_".

Você também pode obter uma lista de todos os posts publicados. Fazemos isso filtrando todos os posts com `published_date` definido no passado:

```text
In [12]: from django.utils import timezone                                        

In [13]: Post.objects.filter(published_date__lte=timezone.now())                  
Out[13]: <QuerySet [<Post: Postagem 2>]>
```

Neste caso de exemplo, temos um dos nossos posts estão publicados ainda. Nós podemos adicionar novos! Primeiro, obtenha a postagem que queremos publicar. No comando abaixo, pegaremos o "Postagem 1", que foi o primeiro a ser criado:

```text
In [14]: post = Post.objects.get(id=1)
```

E então publicamos com o nosso método de publish!

```text
In [15]: post.publish()
```

Agora tente obter a lista de posts publicados novamente \(pressione a seta para cima botão 3 vezes e tecle `Enter`, ou digite o comando novamente\):

```text
In [16]: Post.objects.filter(published_date__lte=timezone.now())
Out[16]: <QuerySet [<Post: Postagem 1>, <Post: Postagem 2>]>
```

