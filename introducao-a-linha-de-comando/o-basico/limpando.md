# Limpando

Não queremos deixar uma bagunça, então vamos remover tudo o que fizemos até agora.

Primeiro, precisamos voltar para nosso workspace \(área de trabalho\):

```text
$ cd ..
```

Fazendo `cd` para **..** nós mudaremos do diretório atual para o diretório pai \(que significa o diretório que contém o diretório em questão\).

Veja onde você está:

```text
$ pwd
/workspace/dg-workspace
```

Agora é hora de excluir o diretório **minhapasta**.

**Atenção:** A exclusão de arquivos usando `del`, `rmdir` ou `rm` é irrecuperável, significando a_rquivos excluídos vão embora para sempre!_

Então, tenha cuidado com este comando.

```text
$ rm -r minhapasta
```

Pronto! Para ter certeza que a pasta foi excluída, vamos checar:

```text
$ ls
```

Por enquanto é isso!

