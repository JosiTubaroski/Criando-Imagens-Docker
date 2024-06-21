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



