# Branch

\
Para copiar um repositório de uma branch que não seja a main (ou master, dependendo da configuração), você pode usar o comando `git clone` seguido pelo URL do repositório e o nome da branch que deseja clonar. Aqui está um exemplo:

```bash
git clone -b nome_da_branch URL_do_repositorio
```

Por exemplo, se você quiser clonar a branch "development" de um repositório, o comando seria algo assim:

```bash
git clone -b development https://github.com/exemplo/repositorio.git
```

Isso irá criar uma cópia do repositório remoto no seu sistema local, mas apenas da branch especificada. Se você não especificar a branch usando a opção `-b`, o Git irá clonar a branch padrão do repositório, que geralmente é a main ou master.

