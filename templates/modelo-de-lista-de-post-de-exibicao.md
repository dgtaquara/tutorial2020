# Modelo de lista de post de exibição

No capítulo anterior, nós fornecemos ao nosso template uma lista de postagens e a variável posts. Agora vamos exibir em nosso HTML.

Para exibir uma variável no Django template, nós usamos colchetes duplos com o nome da variável dentro, exemplo:

```text
{{ posts }}
```

Tente fazer isso no seu template `blog/templates/post_list.html`

Substituia o segundo e o terceiro par de tags `<div></div>` pela linha `{{ posts }}`, salve o arquivo e atualize a página para ver os resultados:

![Tela de informa&#xE7;&#xF5;es a respeito dos nossos posts](../.gitbook/assets/image%20%2810%29.png)

Você pode ver, tudo que temos é algo parecido com:

```text
<QuerySet [<Post: Postagem 1>, <Post: Postagem 2>]>
```

Isto significa que o Django a entende como uma lista de objetos. Lembre-se de **introdução ao Python** como podemos exibir listas? Sim, com os loops! Em um template Django, fazemos isso da seguinte maneira:

```text
{% for post in posts %}    {{ post }}    {% endfor %}
```

Tente fazer isso no seu template.

![Tela de informa&#xE7;&#xF5;es a respeito dos nossos posts](../.gitbook/assets/image%20%2815%29.png)

Funciona! Mas nós queremos que eles sejam exibidos como os posts estáticos, como os que criamos anteriormente no capítulo de **Introdução a HTML**. Nós podemos misturar HTML com tags de template. O conteúdo da `tag body` ficará assim:

```text
<body>
    <div>
        <h1><a href="/">Django Girls Blog</a></h1>
    </div>

    {% for post in posts %}
        <div>
            <p>publicado em: {{ post.published_date }}</p>
            <h1><a href="">{{ post.title }}</a></h1>
            <p>{{ post.text|linebreaksbr }}</p>
        </div>
    {% endfor %}
</body>
```

Tudo que você põe entre o primeiro `{% %}` será repetido para cada objeto na lista. Atualize sua página!! :\)

Você notou que dessa vez nós usamos uma notação um pouco diferente `{{ post.title }}` ou `{{ post.text }}`? Nós estamos acessando os dados em cada um dos campos que definimos no model do Post. Além disso, `|linebreaksbr` está passando o texto do post por um filtro, convertendo quebras de linha em parágrafos.

![Tela do in&#xED;cio de um blog no nosso site](../.gitbook/assets/image%20%286%29.png)

Parabéns! Agora vá em frente e tente adicionar um novo post em seu Django admin \(Lembre-se de adicionar `published_date`!\), em seguida, atualize a página para ver se o post aparece por lá.

Funciona como mágica? Estamos orgulhosos! Afaste-se do seu computador um pouco, você ganhou uma pausa. :\)

![](https://tutorial.djangogirls.org/pt/django_templates/images/donut.png)

