# ¿Cómo instalar?

Para hacer uso de este juego es necesario usar un aplicativo webserver que puede usar archivos estáticos como apache por ejemplo. Simplemente descarga este repositorio y agregalo a la carpeta de tu web server, en el caso de xammp deberá copiarlo a la carpeta htdocs, y desde la dirección localhost/(nombre de la carpeta) e iniciar el archivo index.html


El juego carga un banco de preguntas (por defecto questions.json) en la mismo directorio del archivo index.html. Este archivo contiene las preguntas separadas la cual se describe a continuación.

# ¿Cómo Jugar?

En primera instancia una vez cargue exitosamente el archivo index.html, en la parte superior izquierda aparece una lista de números del 1 al 5 que indica los niveles del juego, seleccionar el nivel deseado y dar click sobre el botón iniciar, ¡Disfrutalo!.

# Web Scraping / Banco de preguntas

Para hacer más fácil la recolección de preguntas, incluí un script de python en la carpeta /util que trae la información desde indiabix.com, lo que hice fue modificar algunas preguntas y dejar el resto tal cual vienen desde la web.

En el directorio raíz está el archivo questions.json el cual contiene las preguntas principales.

# Formato de las preguntas

El banco de preguntas es un array de "games". Se puede tener varios arrays. la estructura es la siguiente:

	{
		"games" : [
			{
				"questions" : [ ... ]
			},
			{
				"questions" : [ ... ]
			}, ...
		]
	}

Cada array de preguntas está en el siguiente formato:


1.	"content" es la clave para los posibles textos de respuestas. "content" debe tener al menos 4 opciones.
2.	La pregunta está localizada en la clave "question".
3.	El index de el valor en "content" que contiene la respuesta correcta está en la clave "correct".

	    {
	    	"question" : "¿Qué significa las siglas TCP?",
		"content" : [
		     "Transmitir Computador Paralelo",
		     "Tasa de Componentes Prácticos",
		     "Protocolo de Control de Transmisión",
		     "Protocolo de Internet"
		 ],
		 "correct" : 2
	     }

# Sonidos y Background

Los sonidos son pequeños fragmentos de audios sacados de la web, para uso ambientador del aplicativo.
