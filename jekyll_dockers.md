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

![image](https://github.com/vNoxpe/iaw/assets/144890599/171b3093-d962-4817-b445-08d0e93990d1)

# 1.1.1 jekyll new
Este comando nos permite crear la estructura de directorios y los archivos necesarios de un nuevo proyecto Jekyll.

docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog

![image](https://github.com/vNoxpe/iaw/assets/144890599/014f88af-eaad-4227-81f3-6c0202f9d5c4)

# 1.1.2 jekyll build

Una vez ejecutado el comado anterior entramos en blog y modificamos el fichero Gemfile porque falta la gema webrick y al tenemos que añadir al final del fichero.

![image](https://github.com/vNoxpe/iaw/assets/144890599/d6b30fba-ea00-41fb-8872-0240025f5f55)

Y despues ejecutamos este comando para instalar la gema que falta.

docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll bash -c "bundle install"

![image](https://github.com/vNoxpe/iaw/assets/144890599/e85a951d-8022-4301-89cc-3d8eb45cdfb8)

Nota: Tenga en cuenta que este comando tendrá que ejecutarlo dentro del directorio donde tenga el contenido del blog.

# 1.1.3 jekyll serve
Este comando nos permite servir de forma local un sitio HTML estático generado a partir del contenido del proyecto Jekyll.

docker run -it --rm -p 4000:4000 -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll serve --force_polling

![image](https://github.com/vNoxpe/iaw/assets/144890599/48dfc385-f3cf-4072-b0d5-90142dde76cb)

La opción --force_polling permite que el contenido del sitio se vaya generando automáticamente cuando existe algún cambio en los archivos del proyecto.

Nota: Tenga en cuenta que este comando tendrá que ejecutarlo dentro del directorio donde tenga el contenido del blog.
# 2 Entramos a la pagina web atraves de http:ip_de_la_maquina:4000

![image](https://github.com/vNoxpe/iaw/assets/144890599/a1cdac16-2340-46bf-a97c-3286d49f6878)
 Y ya abrimos creado una pagina en jekyll con dockers.
