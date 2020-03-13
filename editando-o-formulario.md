# Editando o formulário

Agora já sabemos como adicionar um novo formulário. Mas e se quisermos editar um já existente? É muito semelhante ao que fizemos. Vamos criar algumas coisas importantes rapidamente \(se você não entender alguma coisa - você deve perguntar a uma treinadora ou ver os capítulos anteriores, visto que já cobrimos todas essas etapas anteriormente\).

Abra `blog/templates/post_detail.html` e adicione a linha:

```markup
<a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```

Agora o template \(modelo\) estará parecido com:

```markup
{% extends 'blog/base.html' %}

{% block content %}
    <div class="post">
        {% if post.published_date %}
            <div class="date">
                {{ post.published_date }}
            </div>
        {% endif %}
        <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
        <h1>{{ post.title }}</h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endblock %}
```

Em `blog/urls.py` adicionamos esta linha:

```python
  path(r'^post/(?P<pk>\d+)/edit/$', views.post_edit, name='post_edit'),
```

Nós reutilizaremos o modelo `blog/templates/post_edit.html`, então a última coisa que falta é uma _view_.

Vamos abrir `blog/views.py` e adicionar no final do arquivo:

```python
def post_edit(request, pk):
    post = get_object_or_404(Post, pk=pk)
    if request.method == "POST":
        form = PostForm(request.POST, instance=post)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm(instance=post)
    return render(request, 'blog/post_edit.html', {'form': form})
```

Isso é quase exatamente igual a nossa view de `post_new`, certo? Mas não totalmente. Primeira coisa: passamos um parâmetro extra **pk** de urls . Em seguida: pegamos o modelo Post que queremos editar com `get_object_or_404 (Post, pk=pk)` e então, enquanto criamos um formulário, passamos esta postagem como uma **instância**, ambos quando salvamos o formulário...

```python
form = PostForm(request.POST, instance=post)
```

…e quando nós acabamos de abrir um formulário com essa postagem para editar:

```python
form = PostForm(instance=post)
```

Ok, vamos testar se funciona! Vamos para a página `post_detail`. Deve haver um botão editar no canto superior direito:

![Bot&#xE3;o editar](https://tutorial.djangogirls.org/pt/django_forms/images/edit_button2.png)

Quando você clicar nele você verá o formulário com a nossa postagem:

![Editando o formul&#xE1;rio](https://tutorial.djangogirls.org/pt/django_forms/images/edit_form2.png)

Sinta-se livre para mudar o título ou o texto e salvar as mudanças!

Parabéns! Sua aplicação está ficando cada vez mais completa!

Se você precisar de mais informações sobre formulários do Django você deve ler a documentação: [https://docs.djangoproject.com/en/3.0/topics/forms/](https://docs.djangoproject.com/en/3.0/topics/forms/)

