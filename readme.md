# 📌 Guia Rápido de Comandos Básicos do GitHub

Este guia apresenta comandos essenciais para quem usa **GitHub**. Inclui instalação do GitHub CLI, configuração do Git local e comandos básicos para gerenciar repositórios.

---

## 🖥️ 1. Introdução ao GitHub CLI

O **GitHub CLI** permite interagir com o GitHub diretamente do terminal. Para instalar e usar, siga os passos abaixo:

### 📌 Instalar o GitHub CLI no Windows

Baixe o instalador do GitHub CLI [aqui](https://cli.github.com/).

Após o download, execute o instalador e siga as instruções na tela.

### 📌 Verificar a instalação

```powershell
gh --version
```

Este comando exibe a versão instalada do GitHub CLI.

### 📌 Instalar no Linux (Ubuntu/Debian)

```bash
sudo apt update && sudo apt install gh -y
```

### 📌 Autenticar no GitHub

```powershell
gh auth login
```

Siga as instruções para autenticar sua conta GitHub.

---

## 🚀 2. Configurando o Git Local

Para configurar o Git localmente, siga os passos abaixo:

### 📌 Instalar o Git

- Windows: Baixe o instalador do Git [aqui](https://git-scm.com/downloads).

- Linux (Ubuntu/Debian):

```bash
sudo apt update && sudo apt install git -y
```

### 📌 Configurar o Git com suas credenciais

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```

Esses comandos configuram seu nome e email para os commits.

### 📌 Verificar a configuração

```bash
git config --list
```

Este comando exibe a configuração atual do Git.

### 📌 Configurar o Git no VSCode

No VSCode, digite `Ctrl + ,` para abrir as configurações. Procure por `git.path` e coloque o local de instalação do Git no arquivo `settings.json`. Exemplo:

```json
"git.path": "E:\\Aplicativos\\Git\\bin\\git.exe"
```

### 📌 Testar a instalação do Git

```bash
git --version
```

### 📌 Instalar o GitHub CLI via Winget

```powershell
winget install --id GitHub.cli
```

### 📌 Testar a instalação do GitHub CLI

```powershell
gh --version
```

### 📌 Checar se há uma chave SSH

```bash
ls ~/.ssh/id_rsa.pub
```

### 📌 Criar uma chave SSH

```bash
ssh-keygen -t rsa -b 4096 -C "seuemail@example.com"
```

Isso criará dois arquivos na pasta `C:\Users\SeuUsuario\.ssh\`:

- `id_rsa` → Chave privada (NUNCA compartilhe esse arquivo).
- `id_rsa.pub` → Chave pública (Essa é a que você adiciona ao GitHub).

### 📌 Testar a conexão SSH

```bash
ssh -T git@github.com
```

### 📌 Conectar ao GitHub usando token SSH

```powershell
gh auth login
```

---

## 📁 3. Criando e Gerenciando Repositórios

### 📌 Criar um repositório localmente

```bash
mkdir meu-repo && cd meu-repo
git init -b main
```

Isso cria um repositório Git no diretório atual.

### 📌 Adicionar um repositório remoto

```bash
git remote add origin https://github.com/seu-usuario/meu-repo.git
```

### 📌 Clonar um repositório existente

```bash
git clone https://github.com/seu-usuario/meu-repo.git
```

### 📌 Criar um repositório no GitHub sem fazer push

```bash
gh repo create meu-repo --public --default-branch main
```

### 📌 Criar um repositório no GitHub e fazer push

```bash
gh repo create meu-repo --public --source=. --push
```

### 📌 Testar a conexão com o repositório remoto

```bash
git remote -v
```

---

## 🔄 4. Trabalhando com Commits e Branches

### 📌 Adicionar arquivos ao commit

```bash
git add nome-do-arquivo
# Ou para adicionar todos os arquivos
git add .
```

### 📌 Criar um commit com mensagem

```bash
git commit -m "Mensagem do commit"
```

### 📌 Criar e mudar para uma nova branch

```bash
git checkout -b minha-nova-branch
```

### 📌 Mudar para uma branch existente

```bash
git checkout nome-da-branch
```

### 📌 Listar branches

```bash
git branch
```

---

## 🏷️ 5. Trabalhando com Tags

### 📌 Criar uma nova tag

```bash
git tag -a v1.0 -m "Versão 1.0"
```

Este comando cria uma nova tag anotada com a mensagem "Versão 1.0".

### 📌 Listar todas as tags

```bash
git tag
```

Este comando lista todas as tags no repositório.

### 📌 Enviar tags para o repositório remoto

```bash
git push origin --tags
```

Este comando envia todas as tags locais para o repositório remoto.

### 📌 Deletar uma tag localmente

```bash
git tag -d v1.0
```

Este comando deleta a tag `v1.0` localmente.

### 📌 Deletar uma tag no repositório remoto

```bash
git push origin --delete tag v1.0
```

Este comando deleta a tag `v1.0` no repositório remoto.

---

## 📤 6. Sincronizando com o Repositório Remoto

### 📌 Enviar alterações para o GitHub

```bash
git push origin nome-da-branch
```

### 📌 Atualizar o repositório local com mudanças remotas

```bash
git pull origin nome-da-branch
```

---

## 🔄 7. Gerenciando Merge e Pull Requests

### 📌 Fazer merge de uma branch na branch principal

```bash
git checkout main
git merge minha-nova-branch
```

### 📌 Criar um Pull Request via GitHub CLI

```bash
gh pr create --base main --head minha-nova-branch --title "Novo recurso" --body "Descrição da feature"
```

---

## ❌ 8. Desfazendo Alterações

### 📌 Desfazer alterações antes do commit

```bash
git restore nome-do-arquivo
```

### 📌 Resetar commit localmente

```bash
git reset HEAD~1
```

Remove o último commit, mas mantém os arquivos.

### 📌 Desfazer commit e arquivos

```bash
git reset --hard HEAD~1
```

Remove completamente o último commit e suas alterações.

---

### 🔥 Conclusão

Este guia cobre o essencial do Git e GitHub. Para mais detalhes, use:

```bash
git help <comando>
```

Ou consulte a documentação oficial do Git.

🚀 **Agora é só versionar seu código como um profissional!** 🚀

---

## 📋 Tabela Resumida dos Principais Comandos

| Ação                                      | Comando                                                                                                  | Explicação                                                              |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Instalar Git no Linux**                 | `sudo apt update && sudo apt install git -y`                                                             | Instala o Git no Ubuntu/Debian.                                         |
| **Configurar nome e email**               | `git config --global user.name "Seu Nome"`<br>`git config --global user.email "seuemail@example.com"`    | Configura o nome e email para os commits.                               |
| **Verificar configuração do Git**         | `git config --list`                                                                                      | Exibe a configuração atual do Git.                                      |
| **Criar um repositório local**            | `mkdir meu-repo && cd meu-repo && git init -b main`                                                      | Cria um novo repositório Git local.                                     |
| **Adicionar repositório remoto**          | `git remote add origin https://github.com/seu-usuario/meu-repo.git`                                      | Adiciona um repositório remoto.                                         |
| **Clonar um repositório**                 | `git clone https://github.com/seu-usuario/meu-repo.git`                                                  | Clona um repositório existente.                                         |
| **Adicionar arquivos ao commit**          | `git add nome-do-arquivo`<br>`git add .`                                                                 | Adiciona arquivos ao staging para commit.                               |
| **Criar um commit**                       | `git commit -m "Mensagem do commit"`                                                                     | Cria um commit com uma mensagem descritiva.                             |
| **Enviar alterações para o GitHub**       | `git push origin nome-da-branch`                                                                         | Envia os commits locais para o repositório remoto.                      |
| **Atualizar repositório local**           | `git pull origin nome-da-branch`                                                                         | Atualiza o repositório local com as mudanças do repositório remoto.     |
| **Criar e mudar para uma nova branch**    | `git checkout -b minha-nova-branch`                                                                      | Cria e muda para uma nova branch.                                       |
| **Mudar para uma branch existente**       | `git checkout nome-da-branch`                                                                            | Muda para uma branch existente.                                         |
| **Fazer merge de uma branch**             | `git checkout main && git merge minha-nova-branch`                                                       | Mescla as mudanças de uma branch para a branch principal.               |
| **Desfazer alterações antes do commit**   | `git restore nome-do-arquivo`                                                                            | Desfaz alterações em um arquivo antes do commit.                        |
| **Resetar commit localmente**             | `git reset HEAD~1`                                                                                       | Remove o último commit, mas mantém os arquivos.                         |
| **Desfazer commit e arquivos**            | `git reset --hard HEAD~1`                                                                                | Remove completamente o último commit e suas alterações.                 |
| **Criar um Pull Request**                 | `gh pr create --base main --head minha-nova-branch --title "Novo recurso" --body "Descrição da feature"` | Cria um Pull Request via GitHub CLI.                                    |
| **Testar a conexão SSH**                  | `ssh -T git@github.com`                                                                                  | Testa a conexão SSH com o GitHub.                                       |
| **Verificar status dos arquivos**         | `git status`                                                                                             | Exibe o status atual do repositório, incluindo arquivos modificados.    |
| **Listar branches**                       | `git branch`                                                                                             | Lista todas as branches locais.                                         |
| **Criar um arquivo .gitignore**           | `New-Item .gitignore`                                                                                    | Cria um arquivo .gitignore para especificar arquivos a serem ignorados. |
| **Criar uma nova tag**                    | `git tag -a v1.0 -m "Versão 1.0"`                                                                        | Cria uma nova tag anotada com a mensagem "Versão 1.0".                  |
| **Listar todas as tags**                  | `git tag`                                                                                                | Lista todas as tags no repositório.                                     |
| **Enviar tags para o repositório remoto** | `git push origin --tags`                                                                                 | Envia todas as tags locais para o repositório remoto.                   |
| **Deletar uma tag localmente**            | `git tag -d v1.0`                                                                                        | Deleta a tag `v1.0` localmente.                                         |
| **Deletar uma tag no repositório remoto** | `git push origin --delete tag v1.0`                                                                      | Deleta a tag `v1.0` no repositório remoto.                              |

## Melhores Práticas de Controle de Versão e Commits

### Mensagens de Commit Claras e Descritivas
- **Seja claro e conciso**: A mensagem do commit deve descrever claramente o que foi alterado e por quê.
- **Use o imperativo**: Escreva mensagens de commit no imperativo, como "Adiciona suporte para autenticação".
- **Inclua detalhes relevantes**: Se o commit resolve um bug ou adiciona uma nova feature, inclua detalhes suficientes para que outros desenvolvedores entendam a mudança.

### Commits Pequenos e Frequentes
- **Commits atômicos**: Cada commit deve representar uma única mudança lógica. Isso facilita o rastreamento de bugs e a revisão de código.
- **Commits frequentes**: Faça commits frequentemente para evitar grandes mudanças que são difíceis de revisar e testar.

### Uso de Branches
- **Branches de feature**: Crie uma nova branch para cada nova feature ou bug fix. Isso mantém a branch principal (`main` ou `master`) estável.
- **Nomes de branches descritivos**: Use nomes de branches que descrevam a finalidade da branch, como `feature/autenticacao` ou `bugfix/corrigir-login`.

### Versionamento Semântico
- **Versionamento semântico**: Use versionamento semântico (SemVer) para gerenciar versões do seu projeto. O formato é `MAJOR.MINOR.PATCH`:
  - **MAJOR**: Mudanças incompatíveis na API.
  - **MINOR**: Adição de funcionalidades de forma retrocompatível.
  - **PATCH**: Correções de bugs retrocompatíveis.

### Uso de Tags
- **Tags para versões**: Use tags para marcar versões específicas do seu software. Isso facilita o rastreamento de versões e a criação de releases.
- **Mensagens de tag**: Inclua uma mensagem descritiva ao criar uma tag para explicar o que mudou nessa versão.

### Revisão de Código
- **Pull Requests (PRs)**: Use pull requests para revisar e discutir mudanças antes de mesclá-las na branch principal.
- **Revisão por pares**: Tenha pelo menos uma outra pessoa revisando o código para garantir a qualidade e a detecção de possíveis problemas.

### Automação
- **CI/CD**: Configure pipelines de integração contínua (CI) e entrega contínua (CD) para automatizar testes e deploys.
- **Ferramentas de versionamento**: Use ferramentas como `standard-version` para automatizar o versionamento e a criação de changelogs.

### Exemplo de Mensagem de Commit
```sh
git commit -m "Adiciona suporte para autenticação via OAuth2"
