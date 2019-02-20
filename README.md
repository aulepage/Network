# Faire un daemon à partir d'un script

source : https://thingsmatic.com/2016/06/18/daemonize-that-python-script/

Nous avons besoin de lancer des scripts sous la forme de service (aussi appelés daemon sous linux)
Sous Debian 9, on passe par systemd qui permet d'en créer de nouveau.

Un nouveau service devra comprendre la création d'un fichier avec une extension .service et sera placé dans le dossier suivant :
/etc/systemd/system

Les différentes parties d'un fichier .service dont nous aurons besoin sont notées ci-après :
[Unit]
Partie dans laquelle on peut ajouter une description
[Service]
Rubrique où on doit mettre les possibilités de démarrage du script, comprenant le chemin pour lancer le script (chemin qui doit être absolu)
[Install]
Partie qui traite du lancement du script au démarrage du système

Droits à mettre en place pour le lancement du script :
par défaut, un fichier n'a pas les droits nécessaires pour être lancé comme un éxécutable.
Il faut modifier les droits du fichier comme suit :
Exemple :
```bash
$ sudo chmod +x tempobject.py
```

