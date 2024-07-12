# Comandos Úteis do Git

No repositório é fornecido uma breve base de comandos git, de forma simplificada e rápida, porém recomenda-se um estudo para entender os conceitos do Git e seus comandos, bem como para o que e por que cada um é utilizado.

## Breves Conceitos

**Áreas dos Arquivos:**

  - *Working Directory:* é onde os arquivos são trabalhados e modificados antes de serem adicionados ao stage.

  - *Staging Area:* é onde os arquivos modificados são preparados para o commit. Os arquivos nesta área estão prontos para serem incluídos na próxima confirmação.

  - *Repository:* é o banco de dados do Git onde todos os commits são armazenados permanentemente como histórico do projeto.

**Estados dos Arquivos:**

  - *Untracked:* são arquivos novos no diretório de trabalho que o Git ainda não está rastreando.

  - *Tracked/Unmodified:* são arquivos que já foram commitados e rastreados pelo Git, porém não foram modificados desde o último commit.

  - *Modified:* são arquivos que foram modificados desde o último commit, mas ainda não foram adicionados ao stage.

  - *Staged:* são arquivos que foram modificados e adicionados ao stage, prontos para serem incluídos no próximo commit.

## Outros Conceitos Importantes:

- **Branches:** são ramificações do desenvolvimento do código. Cada branch pode representar uma linha separada de desenvolvimento, permitindo um desenvolvimento paralelo sem interferir na branch principal (normalmente `master` ou `main`), mas pode ser integrado a branch principal durante a linha do tempo.

- **Commits:** são versões de arquivos, pastas e outros componentes dentro do repositório. Cada commit deve ter uma mensagem descritiva que indica as adições e/ou alterações feitas.

<br>

Esses conceitos são fundamentais para compreender como o Git gerencia e controla o código ao longo do tempo, facilitando no entendimento de comandos e seu uso no gerenciamento de versões de software.

***
<br>

## 1. Configurações

### *Configurar o Nome de Usuário Global:*
```
git config --global user.name "<nome>"
```
Adiciona o nome do usuário globalmente dentro das configurações do Git.
- Exemplo com nome: `git config --global user.name "GitHub"`
- Exemplo com username: `git config --global user.name "github067"`

<br>

### *Exibir o Nome de Usuário Configurado:*
```
git config --global user.name
```
Exibe o nome de usuário configurado globalmente no Git.

<br>

### *Configurar o E-mail de Usuário Global:*
```
git config --global user.email "<e-mail>"
```
Adiciona o nome do usuário globalmente dentro das configurações do Git.
- Exemplo: `git config --global user.email "github@gmail.com"`

<br>

### *Exibir o E-mail de Usuário Configurado:*
```
git config --global user.email
```
Exibe o e-mail de usuário configurado globalmente no Git.

<br>

### *Remover o Nome de Usuário Configurado:*
```
git config --global --unset-all user.name
```
Remove o nome das configurações globalmente do Git.

<br>

### *Remover o E-mail de Usuário Configurado:*
```
git config --global --unset-all user.email
```
Remove o e-mail das configurações globalmente do Git.

<br>

### *Lista Todas as Configurações:*
```
git config --list
```
Exibe todas as configurações do diretorio do Git.

<br>

### *Configura o Nome da Branch Padrão:*
```
git config --global init.defaultBranch <nome>
```
Altera o nome da branch padrão do repositório quando o mesmo é criado.

<br>

### *Configura o Editor de Texto do Git:*
```
git config --global core.editor "code --wait"
```
Configura o editor de texto do Git para abrir no VS Code.

<br>

***
<br>

## 2. Manipulação de Repositório

### *Criar Repositório Local*
```
git init
```

### *Verificar Status do Repositório*
```
git status
```

### *Verificar Status no Caminho Atual*
```
git status .
```

### *Adicionar Todos os Arquivos*
```
git add
```

### *Adicionar Arquivos no Caminho Atual*
```
git add .
```

### *Adicionar Arquivo Específico*
```
git add <caminho>
```

### *Remover Todos os Arquivos Rastreáveis*
```
git rm --cached -r .
```

### *Remover Arquivo Específico Rastreável*
```
git rm --cached <caminho>
```

### *Commit de Arquivos*
```
git commit -m "<documentação>"
```

### *Comparar Versão Alterada com Commit mais Recente*
```
git diff
```

### *Comparar Versão Staged com Commit mais Recente*
```
git diff --staged
```

***
<br>

## 3. Histórico de Commits

### *Mostrar Todos os Commits*
```
git log
```

### *Mostrar Histórico Resumido*
```
git log --oneline
```

### *Mostrar Últimos Commits*
```
git log -<quantidade de commits>
```

### *Mostrar Commits com Alterações*
```
git log -p
```

### *Mostrar Commits com Estatísticas*
```
git log --stat
```

### *Mostrar Commits com Estatísticas Resumidas*
```
git log -shortstat
```

***
<br>

## 4. Modificação de Commits

### *Amendar Commit com Nova Mensagem*
```
git commit --amend -m "<documentação>"
```

### *Amendar Commit sem Editar Mensagem*
```
git commit --amend --no-edit
```

### *Amendar Commit com Edição de Mensagem*
```
git commit --amend
```

***
<br>

## 5.  Restauração de Arquivos e Commits

### *Voltar para Commit Específico*
```
git checkout <hash commit>
```

### *Voltar para Commit Mais Recente de uma Branch*
```
git checkout <nome da branch>
```

### *Reverter Estado de Arquivo*
```
git checkout <nome do arquivo>
```

### *Remover Arquivos Não Rastreáveis*
```
git clean -f
```

### *Remover Arquivo da Área de Staging*
```
git restore --staged <nome do arquivo>
```

### *Resetar Alterações*
```
git reset --hard
```

### *Ignorar Arquivo no .gitignore*
```
git update-index --skip-worktree <nome do arquivo>
```

### *Remover Ignorância de Arquivo no .gitignore*
```
git update-index --no-skip-worktree <nome do arquivo>
```

***
<br>

## 6. Clonagem de Repositório

### *Clonar Repositório Online*
```
git clone <url>
```

***
<br>

## 7. Limpeza de Interface

### *Limpar Interface do Git*
```
clear
```

***
<br>

## 8. Arquivo .gitignore

### *Criar Arquivo .gitignore*
```
touch .gitignore
```
