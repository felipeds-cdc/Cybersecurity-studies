# 📘 Guia de Comandos Git & GitHub

> Referência completa: essenciais, diários e resolução de problemas  

---

## 🚀 1. Configuração Inicial (fazer uma vez só)

```bash
# Define seu nome nos commits
git config --global user.name "Seu Nome"

# Define seu email (use o mesmo do GitHub)
git config --global user.email "seu@email.com"

# Define o VS Code como editor padrão
git config --global core.editor "code --wait"

# Visualiza todas as configurações salvas
git config --list
```

---

## 📁 2. Criando e Clonando Repositórios

```bash
# Inicia um repositório Git na pasta atual
git init

# Clona um repositório do GitHub para sua máquina
git clone https://github.com/usuario/repositorio.git

# Clona em uma pasta com nome específico
git clone https://github.com/usuario/repositorio.git minha-pasta
```

---

## 📋 3. Comandos do Dia a Dia

### Verificar status e histórico

```bash
# Mostra o estado atual dos arquivos (modificados, staged, etc.)
git status

# Mostra histórico de commits
git log

# Histórico resumido em uma linha por commit
git log --oneline

# Histórico com gráfico de branches
git log --oneline --graph --all

# Mostra as diferenças dos arquivos modificados
git diff

# Mostra diferenças dos arquivos já em stage
git diff --staged
```

### Adicionar e commitar

```bash
# Adiciona um arquivo específico ao stage
git add arquivo.c

# Adiciona todos os arquivos modificados ao stage
git add .

# Adiciona todos os arquivos de uma extensão
git add *.c

# Cria um commit com mensagem
git commit -m "mensagem descrevendo o que foi feito"

# Adiciona e commita ao mesmo tempo (apenas arquivos já rastreados)
git commit -am "mensagem do commit"
```

### Boas mensagens de commit

```bash
# ✅ Exemplos de boas mensagens:
git commit -m "feat: adiciona formulario de cadastro"
git commit -m "fix: corrige erro de compilacao no main.c"
git commit -m "docs: atualiza README com instrucoes"
git commit -m "refactor: reorganiza funcoes do simulador"

# ❌ Evite mensagens vagas como:
# "update", "fix", "alterações", "commit"
```

---

## 🌿 4. Branches (Ramificações)

```bash
# Lista todas as branches locais
git branch

# Lista branches locais e remotas
git branch -a

# Cria uma nova branch
git branch nome-da-branch

# Troca para uma branch existente
git checkout nome-da-branch

# Cria e já troca para a nova branch (atalho)
git checkout -b nome-da-branch

# Forma moderna de trocar de branch
git switch nome-da-branch

# Cria e troca (forma moderna)
git switch -c nome-da-branch

# Renomeia a branch atual
git branch -m novo-nome

# Deleta uma branch (após merge)
git branch -d nome-da-branch

# Deleta uma branch forçadamente
git branch -D nome-da-branch
```

---

## 🔀 5. Merge e Rebase

```bash
# Une a branch especificada na branch atual
git merge nome-da-branch

# Merge sem fast-forward (mantém histórico da branch)
git merge --no-ff nome-da-branch

# Rebase: reaplica commits em cima de outra branch
git rebase main

# Cancela um rebase em andamento
git rebase --abort

# Continua rebase após resolver conflito
git rebase --continue
```

---

## ☁️ 6. Trabalhando com GitHub (Remoto)

```bash
# Mostra os repositórios remotos configurados
git remote -v

# Adiciona um repositório remoto
git remote add origin https://github.com/usuario/repo.git

# Envia commits para o GitHub (primeiro envio)
git push -u origin main

# Envia commits após o primeiro push
git push

# Envia uma branch específica
git push origin nome-da-branch

# Baixa atualizações do GitHub (sem aplicar)
git fetch

# Baixa e aplica atualizações na branch atual
git pull

# Pull com rebase em vez de merge
git pull --rebase
```

---

## 📦 7. Stash (Guardar mudanças temporariamente)

```bash
# Guarda as mudanças atuais sem commitar
git stash

# Guarda com uma descrição
git stash push -m "trabalho em progresso no formulario"

# Lista todos os stashes salvos
git stash list

# Recupera o stash mais recente e o remove da lista
git stash pop

# Recupera um stash específico
git stash apply stash@{2}

# Deleta o stash mais recente
git stash drop

# Limpa todos os stashes
git stash clear
```

---

## 🏷️ 8. Tags (Versões)

```bash
# Lista todas as tags
git tag

# Cria uma tag simples
git tag v1.0

# Cria uma tag com mensagem (anotada)
git tag -a v1.0 -m "versao 1.0 do simulador"

# Envia tags para o GitHub
git push origin --tags

# Deleta uma tag local
git tag -d v1.0

# Deleta uma tag no GitHub
git push origin --delete v1.0
```

---

## 🔧 9. Resolvendo Problemas Comuns

### Desfazer o último commit (mantendo as alterações)
```bash
git reset --soft HEAD~1
```

### Desfazer o último commit (descartando as alterações)
```bash
git reset --hard HEAD~1
```

### Remover um arquivo do stage (sem deletar o arquivo)
```bash
git restore --staged arquivo.c
```

### Descartar alterações em um arquivo (volta ao último commit)
```bash
git restore arquivo.c
```

### Corrigir a mensagem do último commit
```bash
git commit --amend -m "mensagem corrigida"
```

### Adicionar arquivo esquecido ao último commit
```bash
git add arquivo_esquecido.c
git commit --amend --no-edit
```

### Voltar para um commit específico (sem perder histórico)
```bash
git revert abc1234
```

### Ver quem alterou cada linha de um arquivo
```bash
git blame arquivo.c
```

### Buscar em qual commit um bug foi introduzido
```bash
git bisect start
git bisect bad         # commit atual tem o bug
git bisect good v1.0   # essa versão estava ok
```

---

## ⚔️ 10. Resolvendo Conflitos de Merge

Quando dois commits alteram o mesmo trecho de código, o Git marca o conflito assim:

```
<<<<<<< HEAD
  seu código atual
=======
  código que veio do merge
>>>>>>> nome-da-branch
```

**Passo a passo para resolver:**

```bash
# 1. Veja quais arquivos têm conflito
git status

# 2. Abra os arquivos marcados e edite manualmente
#    Escolha qual versão manter e apague as marcações

# 3. Após corrigir, adicione os arquivos resolvidos
git add arquivo_resolvido.c

# 4. Finalize o merge
git commit -m "fix: resolve conflito no arquivo.c"
```

---

## 🗑️ 11. Limpeza e Manutenção

```bash
# Remove arquivos não rastreados do diretório
git clean -f

# Remove arquivos e pastas não rastreados
git clean -fd

# Visualiza o que seria removido antes de limpar
git clean -n

# Otimiza o repositório local
git gc
```

---

## 🔍 12. Busca e Inspeção

```bash
# Busca um texto em todos os arquivos do projeto
git grep "nome_da_funcao"

# Mostra detalhes de um commit específico
git show abc1234

# Mostra o conteúdo de um arquivo em outro commit
git show abc1234:arquivo.c

# Compara duas branches
git diff main..minha-branch
```

---

## 🌐 13. Fluxo Completo no GitHub

```bash
# 1. Clonar o repositório
git clone https://github.com/usuario/projeto.git

# 2. Criar branch para sua feature
git checkout -b feature/formulario-cadastro

# 3. Fazer alterações e commitar
git add .
git commit -m "feat: adiciona formulario de cadastro"

# 4. Enviar branch para o GitHub
git push origin feature/formulario-cadastro

# 5. Abrir Pull Request no GitHub (pela interface web)

# 6. Após aprovação, atualizar o main local
git checkout main
git pull

# 7. Deletar a branch usada
git branch -d feature/formulario-cadastro
```

---

## 📄 14. .gitignore — Ignorar Arquivos

Crie um arquivo chamado `.gitignore` na raiz do projeto:

```
# Executáveis compilados
*.exe
*.out
programa

# Arquivos de objeto
*.o
*.a

# Pastas de build
build/
Debug/
Release/

# Arquivos de sistema
.DS_Store
Thumbs.db

# Configurações locais do VS Code
.vscode/
```

```bash
# Após criar o .gitignore, adicione e commite
git add .gitignore
git commit -m "chore: adiciona gitignore"
```

---

## ⚡ 15. Atalhos Úteis (Aliases)

```bash
# Cria atalhos para comandos longos
git config --global alias.st status
git config --global alias.lg "log --oneline --graph --all"
git config --global alias.undo "reset --soft HEAD~1"

# Uso após configurar:
git st       # equivale a: git status
git lg       # equivale a: git log --oneline --graph --all
git undo     # equivale a: git reset --soft HEAD~1
```

---

## 📊 Resumo Rápido — Comandos Mais Usados

| Comando | O que faz |
|---------|-----------|
| `git init` | Inicia repositório |
| `git clone <url>` | Clona do GitHub |
| `git status` | Ver estado atual |
| `git add .` | Adiciona tudo ao stage |
| `git commit -m ""` | Salva um commit |
| `git push` | Envia para o GitHub |
| `git pull` | Baixa do GitHub |
| `git branch` | Lista branches |
| `git checkout -b` | Cria e troca de branch |
| `git merge` | Une branches |
| `git stash` | Guarda mudanças temporárias |
| `git log --oneline` | Histórico resumido |
| `git reset --soft HEAD~1` | Desfaz último commit |
| `git restore arquivo` | Descarta alterações |

---

*Guia criado para uso diário em projetos com Git e GitHub*
