# Criando um objeto

É assim que você cria um objeto Post no banco de dados:

```text
In [4]: Post.objects.create(author=eu, title='Título de exemplo', text='Teste')   
---------------------------------------------------------------------------
NameError Traceback (most recent call last)
<ipython-input-4-fcc162ba2291> in <module>
----> 1 Post.objects.create(author=eu, title='Título de exemplo', text='Teste')

NameError: name 'eu' is not defined
```

Mas aqui temos um ingrediente que faltava: **eu**. Precisamos passar uma instância de Usuário modelo como autor. Como fazer isso?

Primeiro vamos importar o modelo User:

```text
In [5]: from django.contrib.auth.models import User
```

Quais usuários temos no nosso banco de dados? Experimente isso:

```text
In [6]: User.objects.all()                                                        
Out[6]: <QuerySet [<User: admin>]>
```

É o superusuário que criamos anteriormente! Vamos obter uma instância de usuário agora:

```text
In [7]: eu = User.objects.get(username='admin') 
```

Como você pode ver, nós agora usamos um `get` no User com o usuário \(_username_\) igual a 'admin'. Claro, você tem que adaptar a seu nome de usuário.

Agora finalmente podemos criar nossa primeira postagem:

```text
In [8]: Post.objects.create(author=eu, title='Título de exemplo', text='Teste')  
Out[8]: <Post: Título de exemplo>
```

Viva! Quer ver se funcionou?

```text
In [9]: Post.objects.all()                                                        
Out[9]: <QuerySet [<Post: Postagem 1>, <Post: Postagem 2>, <Post: Título de exemplo>]>
```

