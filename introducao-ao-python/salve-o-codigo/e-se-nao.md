# E se não?

Nos exemplos anteriores, o código foi executado somente quando as condições eram verdade. Mas o Python também tem instruções `elif` e `else`:

```text
if 5 > 2:
    print('5 é realmente maior que 2')
else:
    print('5 não é maior que 2')
```

Quando for executado irá imprimir:

```text
$ python3 python_intro.py
5 é realmente maior que 2
```

Se 2 for um número maior do que 5, então o segundo comando será executado. Fácil, né? Vamos ver como funciona o `elif`. Substitua seu arquivo com os seguintes comandos \(PS: não vale copiar e colar hein?\): 

```text
nome = 'Sonja'
if nome == 'Ola':
    print('Oi Ola!')
elif nome == 'Sonja':
    print('Oi Sonja!')
else:
    print('Oi anônimo!')
```

e executado:

```text
$ python3 python_intro.py
Oi Sonja!
```

Viu o que aconteceu? O Python comparou o valor da variável `nome` e caiu na condição do `elif` onde compara `nome == 'Sonja'` e assim imprimiu `Oi Sonja!` :D

