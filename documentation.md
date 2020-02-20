# DOCUMENTATION

#### <u>Glossaire / définition</u>

* **Serveur** désigne le serveur de calcul : calculo.rmsb.fr (192.168.10.78)
* **Station** Correspond au mac/PC/ubuntu qui accède au serveur par connexion à distance "ssh"



#### <u>Comment se connecter</u>

A partir de votre station de travail (mac / Ubuntu) qui est connecté au réseau RMSB ouvrir un terminal et executez la commande :

`ssh -Y {accountNextcloud}@calculo.rmsb.fr`

Le mot de passe de votre compte vous sera demandé. Pour ne pas l'écrire à chaque fois sur votre station :

```bash
ssh-keygen
ssh-copy-id atrotier@calculo.rmsb.fr
ssh -Y atrotier@calculo.rmsb.fr
```

Pour avoir accès à l'interface graphique sur mac il faut installer https://www.xquartz.org/.
Pour valider que l'interface graphique fonctionne vous pouvez lancer sur votre connexion à calculo : `xclock` . Une fenêtre avec une horloge devrait s'afficher sur votre station.



Pour lancer matlab il suffit de taper : `matlab &` 
Le symbole & permet de ne pas bloquer le terminal dans lequel vous lancez matlab (mode detach)



#### <u>Comment monter les dossiers sur votre station</u>

Connexion à distance sur les **mac** avec sshfs : 

``` bash
brew tap homebrew/cask
brew cask install osxfuse
brew install sshfs

mkdir /Users/aurelien/calculo # creation d'un dossier où monter le serveur
sshfs atrotier@calculo.rmsb.fr:/home/ /Users/aurelien/calculo -ovolname=calculo
```



Connexion à distance sur les **LINUX** avec ??? : **voir avec Henry **

``` bash

```



#### <u>Architectures des dossiers</u>

Chaque utilisateurs dispose d'un dossier personnel : `/home/atrotier/` 
C'est dans ce dossier qu'il pourra créer et gérer ses codes. Par exemple pour matlab en créant un dossier : `matlab_aurelien`

Les codes communs seront stockés dans : `/home/CODE/`

Example :

* `/home/CODE/gadgetron/`
* `/home/CODE/matlab/`

* `/home/CODE/bart/`



#### <u>Utilisation du serveur avec tmux</u>

tmux est un logiciel installé sur le serveur qui permet d'obtenir plusieurs fenêtre dans la console. Pour le lancer il suffit de taper `tmux` . Cela ouvrira une interface quelques peu différentes que vous pouvez séparer en différents panel / fenêtre. Le principe est que pour activer des raccourcies il faut appuyer sur `ctrl + b` puis une lettre/symbole/touche.

**Toutes les commandes sont disponible dans le fichier DOC/tmux shortcuts & cheatsheet.md**

Exemple : 

`ctrl + b` avant chaque autre symbole :

* **%** sépare la fenêtre vericalement (nouveau panel)
* **"** sépare la fenêtre horizontalement (nouveau panel)
* **c ** Créer une nouvelle fenetre
* tapper exit dans un panel va le quitter (et perdre son historique)
* **d** (pour detach) Pour quitter en conservant son historique (tant que le serveur n'est pas relancer)

Pour relancer une ancienne session `tmux attach`

Pour utiliser la souris dans l'interface il faut installer dans `/home/{nextcloudAccount}/` le fichier  `.tmux.conf`disponible dans le dossier conf de ce répertoire <span style="color:red">**a tester** </span>





#### <u>Utilisation du cahier de laboratoire numérique elabftw</u>

Un cahier de laboratoire est maintenant disponible à l'adresse : https://elabftw.rmsb.fr:8080/

**Attention** : avec chrome il y aura une erreur,  pour s'y connecter il faut cliquer à un endroit de la page et écrire (dans le vide) `thisisunsafe`

L'utilisation du cahier de laboratoire (selon notre méthode de rangement) est décris dans l'annexe `/DOC/elabftw.md` de ce répertoire github



