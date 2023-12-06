---
description: Alguns comandos que ajudaram - Erro de Remote Origin
---

# Comandos - Erros

As vezes queremos atualizar ou adicionar um controle remoto a um repositório Git, mas esse controle remoto já existe. Isso geralmente acontece quando alguém já configurou o controle remoto "origin" anteriormente e acaba dando erro como este:

```bash
git remote add origin https://github.com/juliaRobertav/BackEnd-JRBank.git
error: remote origin already exists.
```

Se você está tentando atualizar e fazer commit em um repositório Git em outro computador, primeiro verifique se você já configurou o controle remoto corretamente. Você pode fazer isso executando o seguinte comando:

```bash
git remote -v
```

Este comando mostrará os URLs dos controles remotos configurados para o seu repositório. Se o controle remoto "origin" já estiver configurado, você não precisará adicioná-lo novamente.

Se você realmente precisar adicionar um controle remoto diferente ou corrigir o URL do controle remoto existente, você pode fazer o seguinte:

```bash
git remote set-url origin URL
```

Substitua o URL acima pelo URL correto do seu repositório. Isso atualizará o URL do controle remoto "origin" para o novo valor.

Depois de corrigir o controle remoto, você pode continuar com os comandos usuais para atualizar e fazer commit no seu repositório Git:

```bash
git pull origin branch_name
git add .
git commit -m "Sua mensagem de commit aqui"
git push origin branch_name

```



Outro erro que pode acontecer é o "refusing to merge unrelated histories" ocorre quando você está tentando mesclar duas histórias (histórias de commit) que não têm um ancestral comum. Isso pode acontecer quando você inicializa um repositório localmente e, em seguida, tenta puxar do repositório remoto, que tem uma linha do tempo de commits diferente.

Se você estiver enfrentando esse problema e estiver certo de que deseja unir as histórias, você pode forçar a mesclagem usando a opção `--allow-unrelated-histories`. Aqui está como você pode fazer isso:

```bash
git pull origin main --allow-unrelated-histories
```

Este comando permitirá que o Git una as histórias mesmo que elas sejam consideradas não relacionadas. Após isso, você pode continuar com os comandos usuais para adicionar, commitar e empurrar as alterações.



Além disso mais um erro é quando há alterações no repositório remoto que você não possui localmente. É importante garantir que seu repositório local esteja atualizado antes de tentar fazer um push.

O comando `git pull origin main` ajudará a puxar as alterações do repositório remoto para o seu repositório local. Se houver conflitos, será necessário resolvê-los manualmente.

```bash
git pull origin main
```

Depois de puxar as alterações, você pode tentar fazer o push novamente:

```bash
git push origin main
```



Também pode ocorrer casos de querer trocar a main ou o repo que irá adicionar seus arquivos, no meu caso, eu queria trocar o repo, então fiz com este passo a passo:

* **Certifique-se de ter um backup:** Antes de fazer grandes alterações, é sempre uma boa ideia ter um backup dos seus dados importantes.
* **Crie uma nova branch:** Se você estiver na branch `main`, pode criar uma nova branch para trabalhar no seu projeto. Isso permitirá que você mantenha a `main` intacta enquanto trabalha na sua nova branch. Use o comando:

```bash
git checkout -b nova_branch
```

Substitua "nova\_branch" pelo nome que desejar.

* **Adicione seus arquivos e faça commit:** Adicione seus arquivos ao repositório e faça um commit na nova branch:

```bash
git add .
git commit -m "Primeiro commit do meu projeto"
```

* **Conecte a nova branch a um novo repositório:** Crie um novo repositório em um serviço Git (por exemplo, GitHub, GitLab, Bitbucket) e siga as instruções fornecidas para adicionar um repositório remoto.

```bash
git remote add origin URL_do_novo_repositorio
```

Substitua "URL\_do\_novo\_repositorio" pela URL do seu novo repositório.

* **Empurre a nova branch para o novo repositório:** Faça o push da sua nova branch para o novo repositório:

```bash
git push -u origin nova_branch
```

Isso enviará sua nova branch com seus arquivos para o novo repositório.

* Agora você tem sua branch `main` no repositório original e uma nova branch no novo repositório. Certifique-se de que o novo repositório esteja configurado corretamente e que você tenha permissões para fazer push. Se você deseja remover completamente a conexão com o repositório original, pode simplesmente excluir o diretório local (se não houver alterações importantes) ou remover o controle remoto:

```bash
git remote remove origin
```

Depois disso, você pode trabalhar na nova branch sem afetar a `main` no repositório original.



Erro quando se executa o comando `git remote add origin` mais de uma vez:

Se você já tem um controle remoto chamado "origin" e deseja alterar o URL associado a ele, em vez de adicionar um novo, você pode usar o seguinte comando:

```bash
git remote set-url origin URL
```

Isso substituirá o URL associado ao controle remoto "origin" pelo novo URL que você forneceu.

Se, por algum motivo, você quiser remover completamente o controle remoto existente e adicionar um novo, você pode fazer o seguinte:

```bash
git remote remove origin
git remote add origin URL
```

O erro indica que você já tem um controle remoto chamado "origin" configurado para o seu repositório local. Isso geralmente acontece quando você executa o comando `git remote add origin` mais de uma vez.

Se você já tem um controle remoto chamado "origin" e deseja alterar o URL associado a ele, em vez de adicionar um novo, você pode usar o seguinte comando:

```bash
git remote set-url origin URL
```

Isso substituirá o URL associado ao controle remoto "origin" pelo novo URL que você forneceu.

Se, por algum motivo, você quiser remover completamente o controle remoto existente e adicionar um novo, você pode fazer o seguinte:

```bash
git remote remove origin
git remote add origin URL
```

Isso removerá o controle remoto existente chamado "origin" e, em seguida, adicionará um novo com o URL fornecido.

Depois de ter configurado corretamente o controle remoto, você pode prosseguir com o push:

```bash
git push -u origin sua_branch
```

Substitua "sua\_branch" pelo nome real da sua branch. Certifique-se de que a nova branch que você criou e na qual está trabalhando seja a que você está tentando enviar para o repositório remoto.

\*Lembre-se que onde está escrito URL é a url do seu repo!
