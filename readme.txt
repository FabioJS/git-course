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
git remote add origin https://github.com/FabioJS/repositorio.git - Origin é o nome default dorepositório mas que pode ser alterado
git branch -M master - Cria a branch para o repositório
git push -u origin master - Envia os arquivos remotos para o repositório do github (origin - nome do repositório remoto, master - nome da branch)

- Clonando repositórios do seu perfil
git clone https://github.com/FabioJS/repositorio.git

- Fork de um repositório. O fork é uma cópia de repositório de outro usuário para que você possa trabalhar nele e então enviar uma pull request quando finalizar as alterações.
- Basta clicar no botão 'Fork' no canto superior direito da tela quando quiser copiar algum repositório.


branch - um ponteiro para um commit. São as 'ramificações' do repositório. Cada branch é uma cópia do que está no repositório master
- Criando uma nova brach
git checkout -b nome-branch
git branch - exibe as branchs existentes e coloca um * naquela que está sendo usada
- Para trocar de branch
git checkout nome-branch
- Deletando uma branch
git branch -D nome-branch
- Unindo as branchs
merge - Vai unir as duas partes, buscando não perder as alterações da branch nem do master. Caso o master tenha recebido um novo commit, é criado um commit para fazer o merge com a branch, sendo que esse segundo commit não terá alterações, apenas vai unir a branch buscando as últimas alterações do master.
git merge nome-branch (mais usado em pull request)
rebase - No caso de novos commit terem sido feitos, irá mover a ramificação desatualizada para o final da ordem, como se a branch tivesse se originado a partir do último commit. Deixa o histórico em forma linear (perde a ordem cronológica das alterações).
git rebase nome-branch (melhor de usar pois não cria commits desnecessários)

- Arquivo .gitingnore
Define os padrões para arquivos que não devem ser enviados ao repositório
.json - ignora arquivos json
arquivo.json - ignora o arquivo específico

- Guardando alterações em andamento
git stash - guarda os arquivos em uma pasta temporária para serem recuperados depois quando necessário
git stash apply - Volta os arquivos armazenados na pasta temporária
git stash list - Lista os arquivos em stash
git stash clear - Limpa a pasta de arquivos em stash

- Criando alias para os comandos do git
git config --global alias.sts status - Cria o álias sts para o comando status nas configurações globais

- Criando tags para versinamento
git tag -a 1.0.0 -m "Versão 1.0.0" - '-a' indica que é uma notação
git push origin master --tags - Adiciona as tags ao repositório