# Suas próprias funções

Se lembra de funções como `len()` que você pode executar no Python? Bem, boas notícias, agora você vai aprender a escrever suas próprias funções!

Uma função é uma sequência de instruções que o Python deve executar. Cada função em Python começa com a palavra-chave `def`, seguido de um nome para a função e opcionalmente uma lista de parâmetros \(informações a serem passadas na hora da função ser chamada, que podem ser usadas em condições etc\). Vamos começar com uma função simples. 

**Substitua** o código no **python\_intro.py** com o seguinte:

```text
def oi():
    print('Olá!')
    print('Como vai você?')
oi()
```

Ok, nossa primeira função está pronta!

Você pode se perguntar por que escrevemos o nome da função na parte inferior do arquivo. Isto é porque Python lê o arquivo e executa de cima para baixo. Então, para usar a nossa função, temos de escrevê-lo na parte inferior.

Vamos executa-lo agora e ver o que acontece:

```text
$ python3 python_intro.py
Olá!
Como vai você?
```

Isso foi fácil! Vamos construir nossa primeira função com parâmetros. Usaremos o exemplo anterior - uma função que diz 'Olá' para quem o executa - com um nome:

```text
def oi(nome):
```

Como você pode ver, agora demos um parâmetro chamado nome para nossa função:

```text
def oi(nome):
    if nome == 'Nome':
        print('Oi Nome!')
    elif nome == 'Sonja':
        print('Oi Sonja!')
    else:
        print('Oi anônimo!')

oi()
```

Como você pode ver, nós precisamos colocar quatro espaços antes da função print, identando-a, porque o `if` precisa saber o que deve acontecer quando a condição for atendida. Vamos ver como isso funciona agora:

```text
$ python3 python_intro.py
Traceback (most recent call last):
File "python_intro.py", line 10, in <module>
  oi()
TypeError: oi() missing 1 required positional argument: 'nome'
```

Oops, um erro. Felizmente, Python nos fornece uma mensagem de erro bastante útil. Ela diz que a função oi\(\) \(aquela que declaramos\) tem um argumento obrigatório \(chamado nome\) e que nós esquecemos de passá-lo ao chamar a função. Vamos corrigi-lo na parte inferior do arquivo:

```text
oi("Nome")
```

e execute novamente:

```text
$ python3 python_intro.py
Oi Nome!
```

E se mudarmos o nome?

```text
oi("Sonja")
```

e executá-lo:

```text
$ python3 python_intro.py
Oi Sonja!
```

Agora, o que acha que vai acontecer se você escrever outro nome lá? \(Sem ser Nome ou Sonja\). Experimente e veja se você está certo. Ele deve imprimir isto:

```text
Oi anônimo!
```

Isto é incrível, não? Dessa maneira você não precisa se repetir \(**DRY - don't repeat yourself**, ou em português, não se repita\) cada vez que for mudar o nome da pessoa que a função pretende cumprimentar. E é exatamente por isso que precisamos de funções - você nunca quer repetir seu código!

Vamos fazer algo mais inteligente..--existem mais que dois nomes, e escrever uma condição para cada um seria difícil, certo?

```text
def oi(nome):
    print('Oi ' + nome + '!')
oi("Maria")
```

Vamos chamar o código agora:

```text
$ python3 python_intro.py
Oi Maria!
```

Parabéns! Você acabou de aprender a criar funções :\)!

