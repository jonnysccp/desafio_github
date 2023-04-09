###Criando uma chave publica SSH para o GITHUB###

**Pergunta padrão: para quê ou por que configurar uma chave SSH. é uma forma de estabelecer uma conexão segura e incriptada entre duas maquinas no meu caso "minha maquina local x servidor github", além de ser uma forma mais segura trata-se de ser uma forma mais rápida para se autenticar. com certeza existe mas fatores positivo mas irei abordar apenas esses que eu identifiquei como os principais.**

Sem mais conversas vamos ao passo a passo para configurar a nossa chave SSH no GITHUB

1. presumindo que você já tenha o git bash na sua maquina, deve-se acessar o git bash e digita o comando "ssh-keygen -t ed25519 -C seu_email" após rodar esse comando o mesmo ira pedir um local para salvar recomendo apenas dar o enter e deixar salvar no local padrão já predefinido pelo git, e logo depois o mesmo solicitara uma senha.

   - exemplo: "ssh-keygen -t ed25519 -C jgreyconsilva@gmail.com".

   - observação ("ed25519" é o tipo de criptografia da chave) com o comando cat id_ed25519.pub conseguimos visualizar a nossa chave publica, vale lembrar que para executar o comando precisamos acessar a pasta onde está as chaves .pub pelo git bash e utilizar o comando cat eu mencionei acima o "cat id_ed25519" mas pode ser qualquer outro nome, o importante que seja a sua chave gerada. 

2. logo após rodar o comando acima o mesmo aparecera a sua chave SSH copie a mesma para que possamos adicionar a mesma ao seu github

3. presumindo que você já tenha uma conta no gitbub se não tiver e fácil e simples para criar vou deixar o link https://github.com/signup

4. você vai acessar suas configurações em --> Settings --> SSH and GPG Keys --> New SSH Key

5. ai você irá adicionar um tittle e depois em key type (tipo de autenticação) = "Authentication Key" e por ultimo a Key que é a chave que voce gerou e conseguiu visualizar no passo 3

6. voltando ao git bash devemos acessar as pastas onde estão as chaves e iremos executar o comando "eval $(ssh-agent -s)" para rodar o processo em segundo plano.

7. com o comando ssh-add id_ed25519 adicionamos a nossa chave para o agent, vale lembrar quando eu mencionei acima o "cat id_ed25519" mas pode ser qualquer outro nome, o importante que seja a sua chave gerada.
   fim.