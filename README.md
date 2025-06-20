
# DIO | Resumos Git e GitHub

## 1. Introdução
   - **Git**
     - Sistema de controle de versão distribuído
     - Usado para gerenciar e versionar código localmente
   - **GitHub**
     - Plataforma de hospedagem de repositórios Git na nuvem
     - Facilita o compartilhamento, colaboração e armazenamento de repositórios

## 2. Diferenças entre Git e GitHub
   - **Git**
     - Ferramenta local de controle de versão
     - Não requer conexão com a internet para funcionar
     - Comandos para gerenciar commits, branches e histórico
   - **GitHub**
     - Hospeda repositórios Git remotamente
     - Requer conta na plataforma
     - Permite colaboração, pull requests, issues e documentação

## 3. Como começar um repositório local
   - **Passo a passo**
     - Navegar para a pasta do projeto:
       ```bash
       cd /caminho/do/projeto
       ```
     - Inicializar o repositório:
       ```bash
       git init
       ```
     - Configurar o nome e e-mail (primeira vez ou global):
       ```bash
       git config --global user.name "Seu Nome"
       git config --global user.email "seuemail@exemplo.com"
       ```
   - **Comandos Básicos**
     - `git status`: Verifica o status dos arquivos
     - `git add .`: Adiciona todos os arquivos modificados para o próximo commit
     - `git commit -m "Mensagem do Commit"`: Salva as alterações no repositório local

## 4. Conectar e Verificar Repositório com GitHub
   - **Criar repositório no GitHub**
     - Acesse [GitHub](https://github.com) > Novo Repositório > Nome > Criar Repositório
   - **Conectar o repositório local ao remoto**
     - Adicionar o repositório remoto:
       ```bash
       git remote add origin https://github.com/usuario/repo.git
       ```
     - Verificar a conexão:
       ```bash
       git remote -v
       ```
   - **Autenticação**
     - Configure SSH ou HTTPS para se autenticar
     - Com SSH:
       - Adicionar a chave SSH ao GitHub

## 5. Download e Atualização de Arquivos entre Git e GitHub
   - **Clonar um Repositório do GitHub**
     - Copiar o link do repositório > Clonar no Git local:
       ```bash
       git clone https://github.com/usuario/repo.git
       ```
   - **Baixar Atualizações do Repositório Remoto**
     - Atualizar a cópia local com novas mudanças do GitHub:
       ```bash
       git pull origin main
       ```
   - **Enviar Atualizações para o Repositório Remoto**
     - Após realizar commits, enviar alterações para o GitHub:
       ```bash
       git push origin main
       ```

## 6. Dicas e Boas Práticas
   - **Mensagens de Commit Claras**: Use mensagens descritivas para facilitar o entendimento do histórico
   - **Branches para Funcionalidades**: Crie branches para funcionalidades ou correções
     ```bash
     git branch nome-da-branch
     ```
   - **Pull Requests**: Faça merge de mudanças através de pull requests para revisão e colaboração

## 7. Resumo de Comandos
   - `git init` - Inicializar repositório
   - `git status` - Exibe os Estado do Diretorio e dos Arquivos na area de Trabalho
   - `git add` - Adicionar arquivos para commit
   - `git commit` - Salvar alterações no repositório local
   - `git push` - Enviar commits para o repositório remoto
   - `git pull` - Baixar e integrar alterações do repositório remoto
   - `git clone` - Clonar um repositório remoto
   - `git log` - Usado para rastrear o histórico de Commits de uma branch
   - `git reflog` - Retorna um Historico detalhado dos Commits, incluindo alterações de arquivos

## 8. Revertendo Alterações
  Essas alterações devem ser feitas, preferencialmente, de maneira local e antes de um push para o Repositorio Remoto
  - `rm -rf .git` - Caso tenha Inicializado um repositorio na pasta errada, esse comando excluira o aquivo .git, e revertendo o status do diretorio
  - `git restore` - Caso não haja interesse em NENHUMA das auterações feitas, ou por acidente o arquivo foi modificado, esse comando irá restalrar a ultima versão do arquivo
  - `git commit --amend -m ""` - Caso deseje alterar a MENSAGEM do ULTIMO commit
  - `git reset soft <hash>` - Desfaz o commit dos arquivos POSTERIORES ao do Hash informado, e mantem os arquivos ja preparados na area de preparação
   - `git reset --mixid` - Também desfaz o commit dos arquivos posteriores a hash informada, porem ele retorna os arquivos fora da area de preparação. Eles tem de ser novamente preparados para o commit
   - `git reset --hard` - Ele também usa como referencia a hash para modificar os arquivos posteriores, porém, ele EXLUI PERMANENTEMENTE os arquivos do seu diretorio
  - `git reset <nome-do-arquivo>` - Retira ele da arvore de preparação
  - `git restore --staged <nome-do-arquivo>` - Retira ele da arvore de preparação
