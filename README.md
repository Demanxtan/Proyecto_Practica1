# Proyecto_Practica1
Proyecto de Practica 1 Unab 2025

Agente Difusor de noticias

Requerimientos:
- Docker
- n8n
- ngrok
- google drive

Guía paso a paso

1 Instalar requerimientos

instalaremos Docker Desktop para poder cargar la imagen JSON de n8n; una vez instalado el Docker colocaremos el siguiente comando en la consola (powershell o gitbash) "docker run -d --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n", este comando creara la imagen de n8n dentro del docker desktop y una vez iniciado sera alojado en un puerto LocalHost 

2 Ingreso n8n

Una vez dentro del n8n mediante LocalHost en tu buscador deberas crear o iniciar sesion para acceder a los workflow. Una vez iniciada la sesion, en el home hay que apretar el boton de "create workflow", dentro del flujo nuevo iremos a los "..." y apretaremos la opción "import from file" y seleccionaremos el JSON que esta en el repositorio, una vez cargado trabajar con el flujo y al switch de la barra superior que dice "inactive" a "active", esto ultimo para que el flujo este siempre activo.

#3 Tunel http

para que el flujo trabaje correctamente usaremos ngrok como tunel de conexion, primero descargaremos Ngrok desde su pagina web o la tienda de microsoft (en mi caso lo instale por la tienda de microsoft ya que por la pagina web me daba una alerta de troyano por el antivirus de microsoft), luego hay que crearse una cuenta en su pagina y una vez dentro en la parte de "setup & installation" encontraremos un comando como el siguiente "ngrok config add-authtoken [codigo de autentificación], este codigo lo colocaremos en nuestra consola y ya estara el tunel vinculado a nuestra cuenta, ahora solo colocamos el comando "ngrok http [puerto del docker]" para iniciar la conexion del flujo con los formularios y apis.

recordar utilizar cada vez el link que te proporciona ngrok cambiarlo en el formulario forms en la parte de app script para poder correr el flujo completo.
