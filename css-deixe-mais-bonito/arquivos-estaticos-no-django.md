# Arquivos estáticos no Django

Finalmente, nós iremos ver mais de perto essas coisas que chamamos de **arquivos estáticos**. Arquivos estáticos são todas as suas imagens e arquivos CSS -- arquivos que não são dinâmicos, então seu conteúdo não depende do contexto da requisição e será o mesmo para todos os usuários.

## Onde colocar os arquivos estáticos no Django

Django já sabe onde encontrar os arquivos estáticos para o app padrão "**admin**". Agora, só precisamos adicionar alguns arquivos estáticos para nosso próprio app, `blog`.

Fazemos isso através da criação de uma pasta chamada `static` dentro do aplicativo do blog:

```text
├── blog
│   ├── migrations
│   ├── static
│   └── templates
└── django
```

Django encontrará automaticamente todas as pastas chamadas _"static"_ dentro de qualquer uma das pastas dos seus apps, e será capaz de usar seu conteúdo como arquivos estáticos.

