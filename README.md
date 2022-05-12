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

