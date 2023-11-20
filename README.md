# WIK-DPS-TP02
TP2 DevOps

Voici la liste des commandes à faire :

1/ "git clone https://github.com/Erxansen/WIK-DPS-TP02"

2/ Une fois le répo cloné, il faut build l'image avec le dockerfile.

Le fichier Dockerfile.1 correspond à la première consigne :
"docker build -f Dockerfile.1 -t devops1:latest ."

Le fichier Dockerfile.2 correspond à la dernière consigne (deuxième container) :
"docker build -f Dockerfile.2 -t devops2:latest ."

3/ Maintenant que l'image est build, il reste plus qu'a la run pour lancer un container :
"docker run --name devops1_container -e PING_LISTEN_PORT=7878 -it -p 7878:7878 devops1"
ou
"docker run --name devops2_container -e PING_LISTEN_PORT=7878 -it -p 7878:7878 devops2"
   le -e est pour implémenter une variable d'environnement
   le -p spécifie le port entre la machine local et le container
   le -it est le mode itératif pour accéder au container
             
3/ Une fois le container lancé, il reste plus qu'a vérifier si l'API est bien appelée avec la commande "curl localhost:7878/ping -v" qui retourne "HTTP/1.1 200 OK" avec les headers de la requête.

4/ La commande "curl localhost:7878 -v" retourne "HTTP/1.1 404 Not Found" avec "Content-lenght=0" qui annonce une page vide.