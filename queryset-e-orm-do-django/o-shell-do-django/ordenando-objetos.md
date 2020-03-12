# Ordenando Objetos

Um QuerySet também nos permite ordenar a lista de objetos. Vamos tentar ordenar as postagens pelo campo `created_date`, ou seja, pela data de criação de cada postagem.

```text
In [17]: Post.objects.order_by('created_date')                                    
Out[17]: <QuerySet [<Post: Postagem 1>, <Post: Postagem 2>, <Post: Título de exemplo>]>
```

Você também pode inverter a ordem adicionando - antes de `created_date`, assim, ordenará do último post até o primeiro.

```text
In [18]: Post.objects.order_by('-created_date')                                   
Out[18]: <QuerySet [<Post: Título de exemplo>, <Post: Postagem 2>, <Post: Postagem 1>]>
```

Legal! Você já está pronto\(a\) para a próxima parte! Para fechar o terminal digite:

```text
In [19]: exit()
```

