## Ambiente de testes de Segurança Ofensiva para Pentest Web
### Desenvolvido sobre o Vagrant.

Esses ambiente é uma ambiente desenvolvido para ser usados pelos alunos do curso de pós-graduação em Ethical Hacking & Cyber Security, 
do Centro de Inovação VincIT (Uniciv).</br>
A versão original do *Vagrantfile* que o professor da disciplina apresenta durante o curso apresenta alguns bugs que foram corrigidos nessa 
versão</br>

### Requisitos:

* Instalação do Virtualbox + pack de adicionais de convidados, na última versão.
* Instalação do Vagrant, na última versão.

### Criação do ambiente:

* Criar em "C:\" um diretório com o nome que quiser e colocar o arquivo "Vagrantfile" dentro dele.
* Executar o comando "vagrant init" para iniciar o vagrant, normalmente esse comando cria o Vagrantfile, mas como já teremos ele dentro do 
diretório, irá gerar um erro de que o arquivo já existe, pode ser ignorado.
* Executar o comando "vagrant up" para criar a virtual machine, aguarda a conclusão da criação.

### Comandos do vagrant:
* vagrant init   ---> Cria o Vagrantfile. | Lê o Vagrantfile existente.
* vagrant up     ---> Criar a virtual machine. | Liga a virtual machine.
* vagrant ssh    ---> Acesso ssh da virtual machine.
* vagrant hal    ---> Desliga a virtual machine.
* vagrant reload ---> Reinicia a virtual machine.

### Correção dos bugs:

Há dois bugs nesse ambiente, o primeiro é com a criação do banco de dados do DVWA (Damn Vulnerable Web Application) e o outro bug 
é relacionado a um bug nos testes de XSS do mesmo DVWA, segue abaixo as correções.

* Falha na crição do banco de dados:
Após a criação da virtual machine, conecte nela via ssh (vagrant ssh) e navegue até /var/www/html/conf, substitua o arquivo "config.inc.php" pelo
arquivo que está aqui no repositório, que está corrigido.

* Falha no XSS:
Esse bug não permite que faça uplods de arquivos para o DVWA, o que prejudica os testes de XSS.<br/>
A correção é simples, tem de dar permissão "755" para o diretório raíz da aplicação e para o diretório de uploads.<br/>
chmod 755 /var/www/html
chmod 755 /var/www/html/hackable/uploads


#### Contato:
joaobcfracassi@gmail.com
