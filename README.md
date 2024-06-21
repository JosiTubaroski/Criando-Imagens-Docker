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












