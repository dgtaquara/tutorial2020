# Todos os objetos

Antes, vamos tentar mostrar todas as nossas postagens. Podemos fazer isso com o seguinte comando:

```text
In [1]: Post.objects.all()                                                        
---------------------------------------------------------------------------
NameError Traceback (most recent call last)
<ipython-input-1-09ba15aa7345> in <module>
----> 1 Post.objects.all()

NameError: name 'Post' is not defined
```

Oops! Um erro apareceu. Ele nos diz que não existe algo chamado Post. É verdade -- nós esquecemos de importá-lo primeiro!

```text
In [2]: from blog.models import Post
```

Isso é simples: importamos o modelo Post de dentro do blog.models. Vamos tentar mostrar todas as postagens novamente:

```text
In [3]: Post.objects.all()                                                        
Out[3]: <QuerySet [<Post: Postagem 1>, <Post: Postagem 2>]>
```

É uma lista dos posts que criamos anteriormente! Criamos esses posts usando a interface de administração do Django. No entanto, agora queremos criar novas mensagens utilizando o Python, então como é que fazemos isso?

