
# ASDF

dependencias

apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm6 libgdbm-dev libdb-dev

instalando com asdf

listar plugins
' asdf plugin-list        

ver a versão do plugin a instalar
' asdf list-all <nome do plugin>
  
intalar o plugin
' asdf install ruby 2.6.10

 definir a versão instalada como global
 
asdf global ruby x.x.x

# ruby
  corrigindo erro de ssl
  
  https://github.com/rbenv/ruby-build/discussions/1940
  
 Following the suggestion of @mislav, I compiled OpenSSL 1.1.1 and it worked. I tested on Ubuntu 22.04 and Fedora 36.

Install the dependencies

Ubuntu 22.04:

$ sudo apt install build-essential checkinstall zlib1g-dev

Fedora 36:

$ sudo dnf groupinstall "Development Tools"
$ sudo dnf install perl-core zlib-devel

Download OpenSSL 1.1.1

$ cd ~/Downloads
$ wget https://www.openssl.org/source/openssl-1.1.1o.tar.gz
$ tar xf openssl-1.1.1o.tar.gz

Compile it

$ cd ~/Downloads/openssl-1.1.1o
$ ./config --prefix=/opt/openssl-1.1.1o --openssldir=/opt/openssl-1.1.1o shared zlib
$ make
$ make test
$ sudo make install

Link the system's certs to OpenSSL 1.1.1 directory

$ sudo rm -rf /opt/openssl-1.1.1o/certs
$ sudo ln -s /etc/ssl/certs /opt/openssl-1.1.1o

Install ruby

Use RUBY_CONFIGURE_OPTS=--with-openssl-dir=/opt/openssl-1.1.1o before the command to install the ruby version

$ RUBY_CONFIGURE_OPTS=--with-openssl-dir=/opt/openssl-1.1.1o rbenv install 2.7.6

If you want to make this permanent, add this line to your .bashrc or .zshrc file:

export RUBY_CONFIGURE_OPTS="--with-openssl-dir=/opt/openssl-1.1.1o/"

Then you don't need to use RUBY_CONFIGURE_OPTS=--with-openssl-dir=/opt/openssl-1.1.1o before the command anymore.




# java

## Open JDK

## Como instalar o OpenJDK Java no Ubuntu e seus derivados via PPA
OpenJDK está disponível nos repositórios oficiais das versões mais recentes do Ubuntu e pode ser instalado usando a Central de programas ou usando o comando sudo apt-get install openjdk-8-jdk.

Mas se a sua versão não disponibiliza ele ou você quer a versão mais recente, para instalar o programa no Ubuntu e ainda poder receber automaticamente as futuras atualizações dele, você deve fazer o seguinte:

Passo 1. Abra um terminal (no Unity use as teclas CTRL + ALT + T);
Passo 2. Se ainda não tiver, adicione o repositório do programa com o comando abaixo;

`sudo add-apt-repository ppa:openjdk-r/ppa`

Passo 3. Atualize o gerenciador de pacotes com o comando:

`sudo apt-get update`
Passo 4. Agora use o comando abaixo para instalar o programa;

`sudo apt-get install openjdk-8-jdk`
Passo 5. Se você tiver mais de uma versão do Java instalado em seu sistema, execute o comando abaixo para definir o interpretador Java padrão:

`sudo update-alternatives --config java`
Passo 6. Na tela que aparece, escolha e digite um número para selecionar uma versão do Java e depois tecle enter;

OpenJDK Java no Ubuntu
Passo 7. Para definir o compilador Java padrão, executando o comando a seguir:

`sudo update-alternatives --config javac`
Passo 8. Finalmente confira qual é a versão Java atual, executando:

java -version
Pronto! Agora você já está com a última versão do Java no Ubuntu.

Desinstalando o OpenJDK Java no Ubuntu e derivados
Para desinstalar o OpenJDK Java no Ubuntu e derivados, faça o seguinte:

Passo 1. Abra um terminal;
Passo 2. Desinstale o OpenJDK Java, usando os comandos abaixo;

`sudo apt-get remove openjdk-8-jdk -y
sudo apt-get autoremove`

Fonte



## Como instalar o Oracle Java JDK manualmente no Ubuntu, Linux Mint e derivadas

Assim como as principais distribuições Linux, o Ubuntu, Linux Mint e distribuições derivadas disponibilizam nos seus repositórios oficiais o OpenJDK, que é um Java Development Kit de código aberto totalmente baseado em software livre. O OpenJDK evoluiu bastante com o passar do tempo e atualmente atende às necessidades da maioria dos usuários, porém, há momentos que se faz necessário a utilização do Java proprietário da Oracle.

O Oracle Java SE Development Kit (JDK) é o ambiente de desenvolvimento para a construção de aplicações, applets e componentes utilizando a linguagem de programação Java. Além do compilador Java (javac), o JDK inclui uma JVM privada, o Java Runtime Environment (JRE) e as APIs Java.

>  Mesmo que você queira instalar e utilizar o JDK da Oracle, recomendo que NÃO REMOVA o OpenJDK (que provavelmente já está instalado no seu sistema), evitando assim problemas de dependências de pacotes.

Caso queira utilizar o Java da Oracle no seu sistema, clique no botão abaixo para acessar o site oficial e baixar a versão mais recente do Oracle JDK (ou de versões mais antigas, dependendo da sua necessidade):

Na página que irá se abrir, selecione a aba "Linux" da versão do JDK que pretende instalar e clique no link de download referente ao arquivo x64 Compressed Archive (tar.gz):

> Recomendo utilizar um gerenciador de downloads como o uGet, o Free Download Manager ou mesmo o wget (em linha de comando) para baixar o Oracle JDK, ok?!

Feito isso, abra um terminal e acesse a pasta onde está o arquivo de instalação .tar.gz do JDK. Caso ele esteja na sua pasta "Downloads", por exemplo, basta digitar:`cd /home/$USER/Downloads

