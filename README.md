# Criando Imagens Docker

- A imagem, contem:

  <p>1 - Sistema Operacional</p>
  <p>2 - Bibliotecas</p>
  <p>3 - Arquivos APP (todos que a aplicação precisa para funcionar)</p>
  <p>4 - Variáveis de Ambiente</p>

Uma imagem contém tudo que é necessário para a Aplicação Funcionar, ou seja se voce tem na sua máquina uma imagem com a aplicação rodando, você consegue transferir para outro servidor, sem ter que fazer todas as configurações novamente.

# Conteiners

O conteiner é um ambiente isolado, como uma VM.

Caracteriristicas dos Conteiners:

<p>1 - Isolado</p>
<p>2 - Start/Stop (Isso pode ser feito pelo Docker Desktop)</p>
<p>3 - Considerado um processo que roda dentro de uma máquina

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/01_Start_Stop_Conteiners.png">

Basicamente o conteiner carrega a imagem e executa a aplicação

### Utilizando o APP do Docker.

<p> 1 - Fazer download app.zip / descompactar e salvar em C:</p>

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/02_Baixar_app.png">

<p> 2 - Para verificar e configurar o ambiente, vamos utilizar o VSCode </p>

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/05_Open_Folder.png">

<p> 3 - Abrir a pasta APP </p>

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/04_Selecionar_App.png">

### Instruções docker file

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/06_Instrucoes_Docker_File.png">

### Para a aplicação vamos precisar de uma imagem docker que tenha Node

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/07_Utilizando_Node_Alpine.png">

### Criando o arquivo docker file para utilizar a imagem docker

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/09_Ambiente_Docker.png">

### Após salvar o dockerfile ir para o Terminal (cmd), e entrar no diretório app

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/10_build.png">

### O que este comando está fazendo?

<p>1. 'docker build': Este é o comando principal do Docker usado para construir imagens Docker a partir de um Dockerfile e de um contexto de build.</p>
<p>2. '-t app': O parâmetro '-t app' ou '--tag' é usado para especificar uma tag para a imagem que está sendo construída. No caso deste exemplo, a tag é 'app',
o que significa que a imagem resultante terá o nome 'app'. Tags são usadas para identificar e nomear versões específicas de imagens Docker.</p>
<p>3. '.': O ponto representa o contexto de build atual. O contexto de build é o conjunto de arquivos e diretórios localizados no diretório atual ('c:\app' neste caso)
que são enviados para o Docker daemon durante o processo de construção da imagem. O Dockerfile deve estar localizado neste contexto de build para que o Docker possa localiza-lo 
e utiliza-lo para construir a imagem.</p>

Portanto, quando você executa <b>'docker build -t app.'</b> no diretório <b>'C:\app'</b>.

 - O Docker procura por um arquivo chamado <b>'Dockerfile'</b> dentro do diretório <b>'c:\app'</b>
 - Ele utiliza o conteúdo deste Dockerfile para construir uma nova imagem Docker.
 - A imagem resultante é nomeada como <b>'app'</b> e pode ser referenciada posteriormente usando essa tag.

É importante ressaltar que o comando <b>'docker build'</b> executa uma série de instruções definidas no Dockerfile para configurar o ambiente e instalar dependencias necessárias
para a aplicação ou serviço que será executado na imagem Docker resultante.

### Verificando se a imagem foi criada

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/11_Imagem_Criada.png">

### Executar um contêiner a partir de uma imagem.

<img src="https://github.com/JosiTubaroski/Criando-Imagens-Docker/blob/main/Img/12_Executar_Container_Imagem.png">

<p>1. 'docker run': Este é o comando principal do Docker usado para executar um contêiner a partir de uma imagem.</p>
<p>2.'-it': Estes dois parâmetros combinados:</p>

  - '-i': Mantém o STDIN aberto, permitindo que você interaja como o contêiner.
  - '-t': Aloca um pseudo-TTY (Terminal) que permite que você interaja com o shell do contêiner.

Juntos, '-it' permite que você entre no conteiner e intereja com ele usando um terminal.

<p>3. 'app': É o nome da imagem que será usada para executar o contêiner. No caso deste exemplo, o conteiner será iniciado a partir da imagem com o nome 'app'.</p>

<p>4. 'sh': É o comando que você deseja executar dentro do conteiner. O 'sh' é um shell padrão que está disponivel em muitas imagens base do Docker, incluindo aquelas baseadas
no Alpine Linux ou outras distribuições Linux minimalistas.

## Explicação do Comando

Quando você executa 'docker run -it app sh'

- O Docker procura pela imagem <b>'app'</b> localmente. Se não estiver presente localmente, ele irá baixá-la do Docker Hub (ou registro de imagens configurado).
- O Docker inicia um novo contêiner a partir da imagem 'app'.
- O parâmetro '-it' permite que você intereja com o terninal do conteiner.
- O comando 'sh' é executado dentro do contêiner. Isso abre um shell interativo dentro do contêiner, onde você pode digitar comandos como faria em qualquer shell Linux.

## Uso Prático

- Este comando é Útil para depuração, teste de imagens Docker ou excução de comandos dentro de ambientes controlados pelo Docker.
- Dependendo da imagem 'app' utilizada, o shell padrão pode variar. Em imagens baseadas em Alpine Linux, por exemplo, o shell pode ser 'sh'. Em outras imagens baseadas em distribuições Linux mais completas, como Ubuntu, pode ser 'bash'.
- Uma vez dentro do contêiner, voce pode explorar o sistema de arquivos, instalar pacotes adicionais, executar scripts ou realizar qualquer outra tarefa necessária para testar ou operar a aplicação ou serviço contido na imagem Docker.

Este comando é fundamental para interargir com conteineres Docker de forma interartiva e executar operações especificas dentro do ambiente isolado fornecido pelo Docker.

#### O que é Docker daemon?

O Docker daemon é um componente crucial do ecossistema Docker. Ele é responsável por gerenciar a criação, execução e destribuição de contêiners Docker em uma máquina host. Aqui estão os principais pontos sobre o Docker daemon:

<p>1. Definição: O Docker daemon é um serviço que roda em segundo plano em um sistema operacional hospedeiro (como Linux, Windows ou macOS) e gerencia todos os aspectos do ciclo de vida dos contêineres Docker.</p>

<p>2. Responsabilidades Principais:</p>

  - <b>Gerenciamento de Contêineres:</b> O daemon Docker é responsavel por criar, iniciar, parar e destribuir contêineres Docker conforme solicitado pelo usuário.
  - <b>Gerenciamento de Imagens:</b> Ele também gerencia imagens Docker, que são os modelos de leitura usados para criar contêineres. O daemon baixa imagens do Docker Hub ou de
    outros registros de imagens, armazana-as localmente e as usa criar contêineres.
  - <b>Rede e Armazenamento:</b> O daemon Docker configura e gerencia redes interna que permitem a comunicação entre contêiners e com a rede externa. Além disso, ele gerencia o armazenamento persistente e temporario utilizado pelo contêineres.

<p>3. Interação com o Docker CLI: O Docker daemon expõe uma API que é utilizada pelo Docker CLI (Command Line Interface) e por outras ferramentas e ferramentas que interagem com o Docker. Quando você executa comandos como <b>'docker run'</b>, <b>'docker build'</b>, ou <b>'docker pull'</b>, o CLI envia solicitações para a API do daemon Docker, que então executa as operações necessárias.</p>

<p>4. Configuração e Execução: O daemon Docker é configurado durante a instalação do Docker no sistema operacional. Ele geralmente é iniciado automatico quando o sistema é inicializado e roda continuamente em segundo plano, garantindo que os container possam ser gerenciados de maneira eficiente e segura.</p>

<p>5. Segurança e Isolamento: O Docker daemon executa contêiners em um ambiente isolado, garantindo que cada contêiner tenha seus próprios recursos limitados (como CPU, memória, rede) e que os processos dentro de um contêiner sejam isolados do sistema hospedeiro.

Em resumo, o Docker daemon é o "coração" do Docker, responsável por todas as operações relacionadas a gestão de conteineres e imagens Docker em um sistema operacional. Ele facilita a criação, execução e gerenciamento de aplicações distribuidas e microserviços em ambientes de desenvolvimento e produção.

## O que é Docker CLI?

O Docker CLI (Command Line Interface) é uma interface de linha de comando que permite aos usuários interagirem com o Docker de maneira eficiente e direta através do terminal ou prompt de comando. Aqui estão os principais pontos sobre o Docker CLI:

<p>1.Funcionalidade: O Docker CLI oferece uma série de comandos que permitem aos usuários realizar operações como gerenciar contêineres, imagens, redes e volumes Docker.</p>

<p>2.Comandos Básicos:</p>

- 'docker run': Inicia um novo container a partir de uma imagem.
- 'docker build': Constrói uma nova imagem Docker a partir de um Dockerfile.
- 'docker pull': Baixa uma imagem Docker do Docker Hub ou de outro registro de imagens.
- 'docker ps': Lista os contêiners em execução.
- 'docker images': Lista as imagens Docker disponíveis localmente.
- 'docker network': Gerencia redes Docker.
- 'docker volume': Gerencia volumes Docker para armazenamento persistente.



















