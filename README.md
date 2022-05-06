# NGINX
##
Lo primero que hice es hacer un ### "sudo su"
Seguido de esto intale nginx con el cmd "apt-get install nginx"
Una vez instalado se accede con el cmd "/etc/nginx", y con el cmd "ll" nos muestra todo lo que hay en este directorio.
Aqui se puede ver como funciona:

![paso2](https://user-images.githubusercontent.com/91737963/167151303-85bbcf94-2456-49c5-96e6-060c70fbcea1.png)

![paso1](https://user-images.githubusercontent.com/91737963/167147283-f52469be-009d-4b73-961d-49ab7d554065.png)

Acto seguido seleccionamos sites-available, escribiendo por cmd "cd /etc/nginx/sites-available/". Dentro de este directorio se ve que hay default viendo esto con el cmd "ll" con ello copiamos este default pero con 2 subdirectorios llamados "calculator.kevin.com" y "fallgame.kevin.com". Una vez esto entramos dentro de estos archivos con "vim".

![paso2](https://user-images.githubusercontent.com/91737963/167148946-c41712c3-46ec-4e95-8cf7-5f9799dddd77.png)

Dentro de estos 2 archivos que accedemos modificamos "server_name" donde le llamo calculator.kevin.com y fallgame.kevin.com, otra cosa que hay que modificar es "root var/www/html" donde modifico donde esta escrito html y lo cambio por "calculator" y "fallgame". Después de esto en la parte superior tenemos que quitar donde dice "listen 80 default;" quitando default y en la siguiente linea tambien.

![paso3](https://user-images.githubusercontent.com/91737963/167150344-e386df5f-8947-4d7a-8f16-7e0a372933a6.png)

![paso4](https://user-images.githubusercontent.com/91737963/167150869-bee00c5d-3e2e-474b-882b-76f577cdb349.png)

Una vez modificado guardamos con :wq!. Una vez salido de la modificación nos movemos al directorio sites-enabled  "/etc/nginx/sites-enabled". Dentro de este con el cmd "ll" vemos que hay un default con una ruta. Seguido de esto insertamos "calculator.kevin.com" y "fallgame.kevin.com" dentro de este default con el cmd "sudo ln -s 
../sites-available/default". Acto seguido revisamos si se introdujo todo correcto con el cmd "ls -la"

![paso6](https://user-images.githubusercontent.com/91737963/167151701-9fc52890-5358-457e-9992-aec852a106c4.png)

Seguido de esto accedemos a "/etc/hosts" con nano. Le añadimos 127.0.0.1 calculator.kevin.com fallgame.kevin.com

![paso7](https://user-images.githubusercontent.com/91737963/167153736-f4cb7e88-099e-4af8-a576-fcef8e802f66.png)

Una vez hecho estos cambios nos movemos al directorio "/var/www/" donde contiene HTML. Acto seguido creamos 2 nuevo subdirectores con "mkdir" donde le llamo "calculator" y "fallgame". Una vez creado accedemos con el cmd "cd calculator/" y entramos al HTML con el cmd"vim index.html", dentro de esta introducimos el codigo que encontramos en la pagina https://onehtmlpagechallenge.com/, Lo mismo pasa con fallgame. Una vez realizado todo actualizamos para que se pueda acceder desde el navegador con el cmd "nginx -s reload" y desde el directorio "/etc/nginx/sites-enabled"

![paso8](https://user-images.githubusercontent.com/91737963/167153980-7c4dd791-a459-4b32-a2c5-c53d0eafc54d.png)

A continuación muestros capturas de que la URL "fallgame.kevin.com" como funciona

![paso9](https://user-images.githubusercontent.com/91737963/167155352-86522699-392b-47ef-a027-ebe4242fa1c7.png)

y aqui muestro con la URL "calculator.kevin.com" como funciona

![paso10](https://user-images.githubusercontent.com/91737963/167155364-7e8b6048-dbe0-4b07-a921-28db199a6110.png)

