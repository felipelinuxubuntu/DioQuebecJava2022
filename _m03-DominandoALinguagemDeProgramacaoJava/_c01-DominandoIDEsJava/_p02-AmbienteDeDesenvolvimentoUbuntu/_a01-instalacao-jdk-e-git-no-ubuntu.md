# Instalação JDK e Git no Ubuntu

Nessa aula exclusivamente eu irei baixar o código do GitHub e irei fazer toda a aula no Ubuntu através de uma máquina virtual.

A partir daqui a aula será feita na maquina virtual linux 

## Preparando o repositório para fazer uma colaboração via maquina virtual linux

Bem eu gastei um bom tempo criando a conta no github e no git e tem alguns processos que precisam ser feitos como as chaves ssh do github.

Por conta disso vou ter que rever algumas aulas de git e github.

A aula que estou revendo é Chaves SSH e Token do Curso introdução ao Git e GitHub.

O primeiro comando que executei no Linux foi

ssh-keygen -t ed25519 -C email-do-usuario.

ele gerou uma chave e mostrou o endereço que essa chave será salva, em uma pasta oculta, sabemos que é oculta por conta do *.* antes do nome do diretório.

Apertamos enter e colocamos uma senha, mantive a pasta padrão sugerida pelo git.

Fui para o diretório onde a chave foi salva no passo anterior e usamos o comando cat id_25519.pub para visualizar o conteúdo da chave pública que será utilizada para fazer o cadastro no github, após visualizar a chave podemos copiar ela e colar no campo key no site do **github** na parte de **SSH and GPG keys** no campo **key**.  

apertamos o botão Add SSH key.

Ao fazer isso uma chave é gerada.

Agora retornamos para o cli do Linux e inicializamos o o SSH Agent, que vai lidar com as chaves. O comando para isso é:  
**eval $(ssh-agent -s)**  

O comando **pwd** mostra o caminho completo do diretório que estamos.

Esse comando eval retorna um pid que significa o número de processo da aplicação.  

Agora entregamos a chave para o ssh-agent com o comando:  
ssh-add id_ed25519

Entregamos a chave privada para ser cuidada pelo agent então toda mensagem criptografada que a gente receber esse agente irá descriptografar a mensagem.  

Não podemos usar o comando git clone para trazer projetos via https, temos que usar a partir de agora o comando SSH.

Com essa chave você pode monitorar o uso dela e se suspeitar que ouve uso indevido, você pode excluir ela e refazer todo o processo, para gerar uma nova chave.  

O Github também tem os tokens de acesso.

https://www.digitalocean.com/community/tutorials/como-criar-um-pull-request-no-github-pt

Tutorial para eu fazer um pull-request e contribuir com um projeto que eu fiz um fork.

Tive problemas para fazer um git push depois dessa autenticação ssh..

Resolvi com esse link 

[stackoverflow](https://pt.stackoverflow.com/questions/551419/problemas-ao-realizar-o-push-no-git) 

A explicação do usuário Danizavtz me ajudou a resolver o problema. Agora posso começar a aula sem problemas.

## Intalação do JDK e Git no Ubuntu

Eu já tenho o Git se a Camila atualizar a versão farei isso.

Eu acredito que segui os passos para instalar o Java no curso da Camila e já tenho ele, sei disso porque executei o comando:  
java -version 

Agora tem que configurar o Java Home porque o java já está instalado. Para isso devemos usar o comando abaixo para saber o caminho da instalação do Java  

**sudo update-alternatives --config java** 

Vamos usar o comando para alterar um arquivo:  

sudo gedit ~/.bashrc

colamos a variavel do Java no fim do arquivo, e usamos o comando 

**cat ~/.bashrc** 

Para verificar se aconteceu as alterações no arquivo, no meu caso ocorreu.

A instalação do git eu já havia feito então foi desnecessário realizar

[o link do repositório da Camila Cavalcante com todos os passos](https://github.com/cami-la/curso-dio-dominando-ides-java)

Fim da aula
