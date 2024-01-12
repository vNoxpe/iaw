# 1 Práctica: Creación de blogs con Jekyll y GitHub Pages
Jekyll es un generador de sitios web estáticos que nos permite crear de forma sencilla blogs, sitios webs personales o webs para proyectos. Los sitios webs generados con Jekyll no usan una base de datos, el contenido del sitio web está escrito en archivos de texto plano en formato Markdown (o Textile) y plantillas Liquid.

Jekyll es el motor de GitHub Pages, un servicio que ofrece GitHub a sus usuarios para que puedan publicar sitios webs estáticos alojados en los repositorios que tienen en GitHub.
# 1.1 Creación de un contenedor Docker con Jekyll
Si buscamos la imagen oficial de Jekyll en Docker Hub encontraremos el repositorio oficicial en GitHub.

Existen tres imágenes oficiales con Jekyll:

jekyll/jekyll: Default image.
jekyll/minimal: Very minimal image.
jekyll/builder: Includes tools.
En esta práctica utilizaremos la imagen por defecto jekyll/minimal.

docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/minimal jekyll
# 1.1.1 jekyll new
Este comando nos permite crear la estructura de directorios y los archivos necesarios de un nuevo proyecto Jekyll.

docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog

# 1.1.2 jekyll build
Este comando nos permite generar un sitio HTML estático a partir del contenido del proyecto Jekyll.

docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll build

# 1.1.3 jekyll serve
Este comando nos permite servir de forma local un sitio HTML estático generado a partir del contenido del proyecto Jekyll.

docker run -it --rm -p 4000:4000 -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll serve --force_polling

La opción --force_polling permite que el contenido del sitio se vaya generando automáticamente cuando existe algún cambio en los archivos del proyecto.
