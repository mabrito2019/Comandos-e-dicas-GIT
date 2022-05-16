## Repositório Local

### Criar novo repositório
git init

### Verificar estado dos arquivos/diretórios
git status

## Adicionar arquivo/diretório (staged area)

### Adicionar um arquivo em específico
git add meu_arquivo.txt

### Adicionar um diretório em específico
git add meu_diretorio

### Adicionar todos os arquivos/diretórios
git add .

## Comitar arquivo/diretório

### Comitar um arquivo
git commit meu_arquivo.txt

### Comitar vários arquivos
git commit meu_arquivo.txt meu_outro_arquivo.txt

### Comitar informando mensagem
git commit meuarquivo.txt -m "minha mensagem de commit"

## Remover arquivo/diretório

### Remover arquivo
git rm meu_arquivo.txt

### Remover diretório
git rm -r diretorio

## Visualizar histórico

### Exibir histórico
git log

### Exibir histórico com diff das duas últimas alterações
git log -p -2

### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))
git log --stat

### Exibir informações resumidas em uma linha (hash completa e comentário)
git log --pretty=oneline

### Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)
git log --pretty=format:"%h - %an, %ar : %s"

 - %h: Abreviação do hash;
 - %an: Nome do autor;
 - %ar: Data;
 - %s: Comentário.

### Exibir histório de um arquivo específico
git log -- <caminho_do_arquivo>

### Exibir histórico de um arquivo específico que contêm uma determinada palavra
git log --summary -S<palavra> [<caminho_do_arquivo>]

### Exibir histórico modificação de um arquivo
git log --diff-filter=M -- <caminho_do_arquivo>

O pode ser substituido por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.

### Exibir histório de um determinado autor
git log --author=usuario

### Exibir revisão e autor da última modificação de uma bloco de linhas
git blame -L 12,22 meu_arquivo.txt 

## Desfazendo operações

### Desfazendo alteração local (working directory)
Este comando deve ser utilizando enquanto o arquivo não foi adicionado na staged area.
git checkout -- meu_arquivo.txt

### Desfazendo alteração local (staging area)
Este comando deve ser utilizando quando o arquivo já foi adicionado na staged area.
git reset HEAD meu_arquivo.txt

Se o resultado abaixo for exibido, o comando reset não alterou o diretório de trabalho.
Unstaged changes after reset:
M	meu_arquivo.txt

A alteração do diretório pode ser realizada através do comando abaixo:
git checkout meu_arquivo.txt

## Repositório Remoto

### Exibir os repositórios remotos
git remote
git remote -v

### Vincular repositório local com um repositório remoto
git remote add origin git@github.com:exemplo/projeto-alvo.git

### Exibir informações dos repositórios remotos
git remote show origin

### Renomear um repositório remoto
git remote rename origin curso-git

### Desvincular um repositório remoto
git remote rm curso-git

### Enviar arquivos/diretórios para o repositório remoto
O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.
git push -u origin master

Os demais pushes não precisam dessa informação
git push

### Atualizar repositório local de acordo com o repositório remoto
### Atualizar os arquivos no branch atual
git pull

### Buscar as alterações, mas não aplica-las no branch atual
git fetch

### Clonar um repositório remoto já existente
git clone git@github.com:exemplo/projeto-alvo.git

# Informações Importantes

### Branches
O master é o branch principal do GIT.

O HEAD é um ponteiro especial que indica qual é o branch atual. Por padrão, o HEAD aponta para o branch principal, o master.

### Bisect
O bisect (pesquisa binária) é útil para encontrar um commit que esta gerando um bug ou uma inconsistência entre uma sequência de commits.