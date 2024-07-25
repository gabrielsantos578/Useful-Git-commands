# Comandos Úteis do Git

Neste repositório, é fornecida uma breve base de comandos Git, de forma simplificada e rápida. Recomenda-se o estudo aprofundado para entender os conceitos do Git, seus comandos, bem como o motivo e o cenários correta=os de sua utilização.

## Breves Conceitos

**Áreas dos Arquivos:**

- ***Working Directory:*** * é onde os arquivos são `trabalhados e modificados` antes de serem adicionados ao Stage. {#working_directory}
- ***Staging Area:*** é onde os arquivos modificados são `preparados` para o commit. Os arquivos nesta área estão prontos para serem incluídos na próxima confirmação. {#staging_area}
- ***Repository:*** é o banco de dados do Git onde `todos os commits são armazenados` permanentemente como `histórico do projeto`. {#repository}

**Estados dos Arquivos:**

- ***Untracked:*** são `arquivos novos` no diretório de trabalho, que `não estão rastreados` pelo Git. {#untracked}
- ***Tracked/Unmodified:*** são arquivos que já foram `rastreados` e `commitados` pelo Git, mas `não foram modificados` desde o último commit. {#tracked} {#unmodified}
- ***Modified:*** são arquivos que foram `modificados` desde o último commit, mas ainda não foram adicionados ao stage. {#modified}
- ***Staged:*** são arquivos que foram modificados e `adicionados ao Stage`, prontos para serem incluídos no próximo commit. {#staged}

## Outros Conceitos Importantes:

- ***Branches:*** são `ramificações` do desenvolvimento do código. Cada branch pode representar uma linha separada de desenvolvimento, permitindo um desenvolvimento paralelo sem interferir na branch principal (normalmente `master` ou `main`). Mudanças e alterações feitas nas ramificações podem ser integradas à branch principal durante a linha do tempo. {#branch}

- ***Commits:*** são `versões` de arquivos, pastas e outros componentes dentro do repositório. Cada commit deve ter uma mensagem descritiva que indica as adições e/ou alterações feitas. {#commit}

- ***HEAD:*** é um `ponteiro` especial que indica o commit atual no qual o repositório se encontra no branch ativo, normalmente apontando para o último commit do histórico. No entanto, o HEAD pode apontar para commits mais antigos quando comandos específicos são usados, resultando em um estado conhecido como `detached HEAD`. Observação: um branch sempre irá apontar para o commit mais recente e visível no histórico; por outro lado, o HEAD pode apontar para o mesmo commit ou outros selecionados. {#head}

## Alertas:

- **Alteração do Histórico de Commits:** Ao trabalhar em equipe, é crucial manter a integridade do histórico de commits. Alterações ou reescritas no histórico podem comprometer a rastreabilidade e a colaboração eficaz. Recomenda-se seguir práticas de rebase seguro ou uso adequado de revert e reset para evitar problemas. Quando comandos que sobrescrevem o histórico são utilizados e essas ações são mescladas para o repositório remoto, comunique e entre em acordo com sua equipe.

- **Conflitos:** Conflitos ocorrem quando duas ou mais alterações são feitas na mesma parte de um arquivo ou projeto. Resolver conflitos de maneira inadequada pode levar à perda de trabalho, introdução de erros e atrasos no desenvolvimento. É fundamental comunicar e coordenar alterações entre os membros da equipe para minimizar conflitos e resolver eficientemente quando surgirem. Se eventualmente surgirem conflitos, revise cuidadosamente cada arquivo e aceite as alterações corretas.

<br>

Esses conceitos são fundamentais para compreender como o Git gerencia e controla o código ao longo do tempo, facilitando no entendimento de comandos e seu uso no gerenciamento de versões de software.

***

# Índices 

* [Configurações](#Configurações)
* [Repositório](#Repositório)
* [Arquivos](#Arquivos)
* [Adicionais](#Adicionais)

***
<br>

## Configurações:

**1** - Configura um nome de usuário global.
```
git config --global user.name "<username_ou_apelido>"
```
Exemplo: `git config --global user.name "gabrielsantos578"`
<br><br>

**2** - Configura um e-mail de usuário global.
```
git config --global user.email "<e-mail>"
```
Exemplo: `git config --global user.email "github@gmail.com"`
<br><br>

**3** - Remove o nome de usuário das configurações.
```
git config --global --unset-all user.name
```
<br>

**4** - Remove o e-mail das configurações.
```
git config --global --unset-all user.email
```
<br>

**5** - Lista todas as configurações do git no sistema operacional.
```
git config --list
```
<br>

**6** - Configura a branch padrão para novos repositórios.
```
git config --global init.defaultBranch <nome_branch>
```
Exemplo: `git config --global init.defaultBranch main`
<br><br>

**7** - Configura o VS Code como editor padrão do git.
```
git config --global core.editor "code --wait"
```
<br>

### Abreviações:
<br>

**8** - Cria uma abreviação para um comando.
```
git config --global alias.<abreviacao_comando> <comando>
```
Exemplo: `git config --global alias.s status`
<br><br>

**9** - Cria uma abreviação para um comando maior.
```
git config --global alias.next 'rebase --continue'
```
Exemplo: `git config --global alias.next 'rebase --continue'`
<br><br>

**10** - Remove a abreviação informada.
```
git config --global --unset alias.<abreviacao_comando>
```
Exemplo: `git config --global --unset alias.s`
<br><br><br>

***

## Repositório:

### Clone:
<br>

**11** - Clona um repositório online para o desktop.
```
git clone <url>
```
Exemplo: `git clone https://github.com/user/repo.git`
<br><br>

**12** - Clona um repositório online com nome de pasta específico.
```
git clone <url> <nome>
```
Exemplo: `git clone https://github.com/user/repo.git nome_pasta`
<br><br><br>

### Histórico:
<br>

**13** - Compara a versão modificada com a versão commitada mais recente.
```
git diff
```
<br>

**14** - Compara a versão staged com a versão commitada mais recente.
```
git diff --staged
```
<br>

**15** - Mostra todos os commits e suas informações.
```
git log
```
<br>

**16** - Mostra o histórico de commits em uma linha.
```
git log --oneline
```
<br>

**17** - Mostra os últimos commits informados.
```
git log -<quantidade_de_commits>
```
Exemplo: `git log -10`
<br><br>

**18** - Mostra o histórico de commits da branch informada.
```
git log <nome_branch> --oneline
```
Exemplo: `git log main --oneline`
<br><br>

**19** - Mostra commits, informações e arquivos alterados/adicionados.
```
git log --stat
```
<br>

**20** - Mostra o histórico de commits da branch remota informada.
```
git log origin/<nome_branch> --oneline
```
Exemplo: `git log origin/main --oneline`
<br><br><br>

### Branch:
<br>

**21** - Mostra todas as branches do repositório.
```
git branch --list
```
<br>

**22** - Cria uma nova branch com o nome informado.
```
git branch <nome_branch>
```
Exemplo: `git branch dev`
<br><br>

**23** - Renomeia a branch informada.
```
git branch -m <nome_branch> <novo_nome>
```
Exemplo: `git branch -m dev develop`
<br><br>

**24** - Mostra todas as branches, locais e remotas.
```
git branch -a
```
<br>

**25** - Força a remoção da branch informada.
```
git branch -D <nome_branch>
```
Exemplo: `git branch -D dev`
<br><br>

**26** - Muda para a branch informada.
```
git switch <nome_branch>
```
Exemplo: `git switch dev`
<br><br>

**27** - Cria e muda para a nova branch.
```
git switch -c <nome_branch>
```
Exemplo: `git switch -c feature`
<br><br>

**28** - Muda de branch limpando a atual.
```
git switch -f <nome_branch>
```
Exemplo: `git switch -f main`
<br><br>

**29** - Volta para o commit informado.
```
git checkout <hash_commit>
```
Exemplo: `git checkout a1b2c3d`
<br><br>

**30** - Retorna para o commit mais recente da branch.
```
git checkout <nome_branch>
```
Exemplo: `git checkout dev`
<br><br>

**31** - Reverte o estado do arquivo para o último commit.
```
git checkout <nome_do_arquivo>
```
Exemplo: `git checkout arquivo.txt`
<br><br><br>

### Tags:
<br>

**32** - Cria uma tag no commit atual.
```
git tag <nome_tag>
```
Exemplo: `git tag v1.0`
<br><br>

**33** - Exibe as informações da tag.
```
git show <nome_tag>
```
Exemplo: `git show v1.0`
<br><br>

**34** - Exibe todas as tags e seus commits.
```
git tag -n
```
<br>

**35** - Marca o commit especificado com uma tag.
```
git tag -a -m <mensagem_tag> <nome_tag> <hash_commit>
```
Exemplo: `git tag -a -m "Versão 1.0" v1.0 a1b2c3d`
<br><br>

**36** - Envia todas as tags para o repositório remoto.
```
git push --tags
```
<br>

**37** - Volta o repositório para o estado do commit da tag.
```
git checkout <nome_tag>
```
Exemplo: `git checkout v1.0`
<br><br>

**38** - Remove a tag especificada.
```
git tag -d <nome_tag>
```
Exemplo: `git tag -d v1.0`
<br><br>

**39** - Remove a tag especificada do repositório remoto.
```
git push --delete origin <nome_tag>
```
Exemplo: `git push --delete origin v1.0`
<br><br><br>

### Links/Endereços/URL:
<br>

**40** - Lista todas as URLs associadas ao repositório local.
```
git remote -v
```
<br>

**41** - Adiciona uma nova URL remota.
```
git remote add <palavra-chave> <url>
```
Exemplo: `git remote add origin https://github.com/user/repo.git`
<br><br>

**42** - Atualiza a URL de um repositório remoto existente.
```
git remote set-url <palavra-chave> <url>
```
Exemplo: `git remote set-url origin https://github.com/user/new-repo.git`
<br><br><br>

### Subir:
<br>

**43** - Envia commits locais para o repositório remoto.
```
git push
```
<br>

**44** - Envia commits locais e cria a branch remota se não existir.
```
git push -u origin <nome_branch>
```
Exemplo: `git push -u origin main`
<br><br>

**45** - Força as mudanças locais a sobrescreverem o repositório remoto.
```
git push --force
```
<br>

**46** - Força as mudanças se nenhuma mudança for perdida.
```
git push --force-with-lease
```
Exemplo: `git push --force-with-lease`
<br><br>

**47** - Remove a branch remota informada.
```
git push --delete origin <nome_branch>
```
Exemplo: `git push --delete origin dev`
<br><br><br>

### Descer:
<br>

**48** - Baixa commits do repositório remoto e integra as mudanças.
```
git pull
```
<br>

**49** - Traz mudanças do remoto reescrevendo commits locais.
```
git pull --rebase
```
<br>

### Reversão:
<br>

**50** - Remove o último commit e retorna ao estado anterior.
```
git revert --hard HEAD
```
<br>

**51** - Remove o último commit mantendo as alterações para stage.
```
git revert --mixed HEAD
```
<br>

**52** - Remove o último commit mantendo as alterações para commit.
```
git revert --soft HEAD
```
<br>

**53** - Reverte os últimos <numero> commits.
```
git revert HEAD~<numero>
```
Exemplo: `git revert HEAD~2`
<br><br>

**54** - Reverte o commit especificado.
```
git revert <hash_commit>
```
Exemplo: `git revert a1b2c3d`
<br><br>

**55** - Reverte a reversão especificada.
```
git revert <hash_commit_reversao> --no-edit
```
Exemplo: `git revert a1b2c3d --no-edit`
<br><br><br>

***

## Arquivos:

### Adição:
<br>

**56** - Rastreia todos os novos arquivos e os modificados.
```
git add
```
<br>

**57** - Rastreia todos os novos arquivos e os alterados no caminho atual.
```
git add .
```
<br>

**58** - Rastreia os arquivos no caminho especificado.
```
git add <caminho>
```
Exemplo: `git add src/`
<br><br><br>

### Rastreamento:
<br>

**59** - Mostra novos arquivos não rastreados e os modificados.
```
git status
```
<br>

**60** - Mostra novos arquivos e os modificados no caminho atual.
```
git status .
```
<br>

**61** - Ignora o arquivo especificado.
```
git update-index --skip-worktree <nome_do_arquivo>
```
Exemplo: `git update-index --skip-worktree config.yml`
<br><br>

**62** - Remove a ignorância do arquivo especificado.
```
git update-index --no-skip-worktree <nome_do_arquivo>
```
Exemplo: `git update-index --no-skip-worktree config.yml`
<br><br><br>

### Commit:
<br>

**63** - Salva todos os arquivos rastreados com uma mensagem.
```
git commit -m "<documentacao>"
```
Exemplo: `git commit -m "Initial commit"`
<br><br>

**64** - Adiciona e salva todos os arquivos rastreados modificados.
```
git commit -a -m "<documentacao>"
```
Exemplo: `git commit -a -m "Updated files"`
<br><br>

**65** - Altera o último commit com uma nova mensagem.
```
git commit --amend -m "<documentacao>"
```
Exemplo: `git commit --amend -m "Corrected message"`
<br><br>

**66** - Altera o último commit sem mudar a mensagem.
```
git commit --amend --no-edit
```
<br>

**67** - Abre o editor para alterar o último commit.
```
git commit --amend
```
<br>

### Remoção:
<br>

**68** - Remove todos os arquivos rastreados do índice.
```
git rm --cached -r .
```
<br>

**69** - Remove os arquivos não rastreados.
```
git clean -f
```
Exemplo: `git clean -f`
<br><br>

**70** - Remove todas as alterações não commitadas e volta ao último commit.
```
git reset --hard
```
<br>

### Backup:
<br>

**71** - Salva as mudanças em cache e retorna ao último commit.
```
git stash
```
<br>

**72** - Mostra todas as mudanças salvas em stash.
```
git stash list
```
<br>

**73** - Aplica um stash específico.
```
git stash apply stash@{<id>}
```
Exemplo: `git stash apply stash@{0}`
<br><br>

**74** - Aplica e remove um stash específico.
```
git stash pop stash@{<id>}
```
Exemplo: `git stash pop stash@{0}`
<br><br>

**75** - Remove um stash específico.
```
git stash drop stash@{<id>}
```
Exemplo: `git stash drop stash@{0}`
<br><br><br>

***

## Adicionais:

**76** - Cria um arquivo para configurar arquivos a serem ignorados pelo git.
```
touch .gitignore
```
<br>

**77** - Limpa a interface do git.
```
clear
```
<br>

**78** - Gera uma chave SSH na pasta ~/.ssh/.
```
ssh-keygen
```
<br>

**79** - Inicia um agente SSH.
```
eval $(ssh-agent)
```
<br>

**80** - Adiciona a chave SSH privada ao agente.
```
ssh-add <caminho_chave_privada>
```
Exemplo: `ssh-add ~/.ssh/id_rsa`
<br><br>

**81** - Navega para a pasta informada.
```
cd <caminho>
```
Exemplo: `cd ~/.ssh`
<br><br>

**82** - Abre o VS Code no caminho atual.
```
code .
```
<br>
