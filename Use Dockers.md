1.- sobre todo vamos a  tenerlo todo bien hecho

primero actulizaremos ficheros y demas

sudo apt-get update
sudo apt-get upgrade



2.-Instalar docker

si quieres ver la fuente original.- https://docs.docker.com/install/linux/docker-ce/ubuntu/


si ya habias hecho algun vez un contenedor y usaste el comando snap... puedes usar este comando ya que snap puede traer dockers

sudo snap install docker; 

 si no ;
 
Vamos paso por paso

2.1.- Eliminamos algun docker que tengamos instalado, si no tienes nada o pasas de este paso sin problemas. (Complementario al paso anterior)

  sudo apt-get remove docker docker-engine docker.io containerd runc
  
2.2.- Instalamos los paqutes para que el apt use repositorios sobre HTTPS
 
  sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
 
 2.3.- Necesitamos la clave oficial para el docker:
 
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   
    (si quiers asegurarte de haber obtenido la clave correctamente, es OPCIONAL)
      sudo apt-key fingerprint 0EBFCD88

        pub   rsa4096 2017-02-22 [SCEA]
              9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
        uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
        sub   rsa4096 2017-02-22 [S]
 
 2.4.- Ahora depende del sistema que tengamos tendremos que colocar una cosa u otra
 
 https://docs.docker.com/install/linux/docker-ce/ubuntu/
 Apartado Install docker CE.- numero 4
 
 ![Imgur](https://i.imgur.com/foXzUWK.png)
 
 si usas la version mint debes de colocar otro codigo
 
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
 
 
 2.5.- Volvemos a recargaar y por fin instalamos dockers 
 
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io
 
 2.6.- Ahora comprobamos que todo este bien 
 
  sudo docker run hello-world
 
 
 
 3.- Si queremos eliminar el docker usamos el siguiente comando
 
  sudo apt-get purge docker-ce
  
  pero la gracia es que las imagenes siguen montadas, y para quitarlas tendremos que usar el siguiente comando
  sudo rm -rf /var/lib/docker
 
 -----------------------------------------------------------------------------------------
 
 una vez instalado ya e docker subiremos las imagenes que nos hagan falta
 
 en esta pagina encontraremos las imagenes qque nos hagan falta, y el comando para poder bajarla

 https://hub.docker.com/
 los docker pull  seria conveniente que lo hicieras dentro del directorio y fichero que te interesan
 

