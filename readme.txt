- Conectando ao github com chave ssh
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

- Seguir passo a passo
https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

As chaves ficam no diretório C:\Users\fabin/.ssh/
- Serão criados os arquivos id_rsa e id_rsa.pub com a chave pública
- Copiar a chave criada

No github
- Acessar settings > SSH and GPG keys e adicionar a chave criada

- Estados dos arquivos no git
untracked
unmodified
modified
staged

- Configurando especificações globais do git
git config --global user.name "FabioJS"
git config --global user.email "fabiodossantospy@gmail.com"

- Configurando o editor padrão do git
git config --global core.editor code

- Exibindo as configurações 
git config --global user.name
git config --global user.email
git config --list

- Inicializando o repositório
git init

- Adicionar/commitar arquivos ao commit
git add arquivo.txt
git commit -m "mensagem" - Commitando arquivos
git commit -am "mensagem - Adiciona os arquivos e faz o commit

- Visualizando logs dos commits
git log
git log --decorate
git log --author="FabioJS" - Filtra o autor dos commits
git shortlog - Quantidade de commits de cada contribuinte
git log --graph - Exibe em forma de gráfico as contribuições 
git show c564302e3eb67f3d93651577842ea54a3212c79c - Exibe informações do commit de acordo com o hash de identificação do commit

- Verificando alterações antes de commitar
git diff
git diff --namr-only - Exibe apenas o nome dos arquivos alterados

- Voltando as alterações de um arquivo
git checkout arquivo.txt
- Voltar arquivo que já foi adicionado na área de commit (staged)
git reset HEAD arquivo.txt
- Voltar arquivos já commitados
git reset --soft c564302e3eb67f3d93651577842ea54a3212c79c- Reverte as alterações posteriores ao commit desse hash e volta o arquivo com as alterações para a área de staged (antes de efetivar o commit)
git reset --mixed c564302e3eb67f3d93651577842ea54a3212c79c - Reverte as alterações posteriores ao commit desse hash e volta o arquivo para antes da área de staged (precisa adicionar novamente o arquivo com git add para fazer commit de novo)
git reset --hard c564302e3eb67f3d93651577842ea54a3212c79c - Reverte as alterações posteriores ao commit desse hash e apaga demais informações do commit (não volta o arquivo para a situação anterior ao commit, somente apaga as alterações já feitas [cuidado ao usar, pode dar problemas])


- Criando repositório remoto
git remote add origin https://github.com/FabioJS/repositorio.git
git branch -M master - Cria a branch para o repositório
git push -u origin master - Envia os arquivos remotos para o repositório do github


