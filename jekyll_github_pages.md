# Instalación del tema minima en GitHub Pages

## 1ºPaso.Preparación Máquina virtual en Debian 12
Configuración IPv4: /etc/network/interfaces

auto lo

iface lo inet loopback

#Configuración IPv4

auto enp0s3

#allow-hotplug enp0s3

iface enp0s3 inet static

#iface enp0s3 inet dhcp

address 10.0.16.202

netmask 255.255.255.0

gateway 10.0.16.254

dns-nameservers 10.0.1.48 10.0.1.54

dns-domain iesmhp.local

## 2ºPaso - Conexión remota desde Windows a Debian 12:

Utilizamos el comando ssh hugo@10.0.16.202 para conectar el git bash con la maquina debian12

## 3ºPaso Instalación prerrequisitos en la maquina debian 

sudo apt-get update -y

sudo apt update -y

sudo apt-get install ruby-full build-essential zlib1g-dev

Ahora ecribimos esto en la terminal de gitbash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc

echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc

echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.
bashrc

source ~/.bashrc

Y ejecutamos el comando gem install jekyll bundler

## 4ºPaso.Creación del repositorio local
 utilizamos los siguientes comandos para crear el repositorio en local 
 rnativa 2:
mkdir myblog

cd myblog

git init

git remote add origin https://github.com/vNoxpe/myblog.git

: Si se desea publicar el sitio desde la rama gh-pages, creamos y desprotejemos la
rama con el siguiente comando:

git checkout -b gh-pages

## 5ºPaso.Creación del sitio en Jekyll:
Para la creación de un proyecto jekyll con todo lo necesario (archivos, carpetas, plantillas, etc) basado en el tema minima usamos el siguiente comando (con el que se crea el directorio myblog y genera el sitio jekyll):

jekyll new myblog

## 6ºUltimo paso:Prueba del sitio localmente:
 Para hacer la prueba utilizamos el comando 
 
bundle exec jekyll serve --host ip del equipo --port 3000 