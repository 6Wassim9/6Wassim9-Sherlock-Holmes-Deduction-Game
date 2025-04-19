# Sherlock Holmes Deduction Game



Une implémentation réseau en C/SDL2 d'un jeu de déduction inspiré de l'univers de Sherlock Holmes pour **4 joueurs**, où chacun tente de découvrir qui est le coupable parmi 13 personnages.



---



## Prérequis



- **Linux** (Ubuntu/Debian recommandé)

- **GCC** (ou tout compilateur C compatible)

- **SDL2**, **SDL2_image**, **SDL2_ttf**, **pthread**



### Installation des dépendances (Debian/Ubuntu)

```bash

sudo apt-get update

sudo apt-get install build-essential libsdl2-dev libsdl2-image-dev libsdl2-ttf-dev

```



---



## Compilation



Le projet contient un **Makefile** prêt à l'emploi.



1. Placez-vous à la racine du dossier `PROJET` :

   ```bash

   cd ~/chemin/vers/PROJET

   ```

2. Compilez tout avec :

   ```bash

   make

   ```

3. Pour tout nettoyer (binaries) :

   ```bash

   make clean

   ```



---



## Exécution



### 1) Lancer le serveur



```bash

./server <port>

# Exemple :

./server 5000

```



### 2) Lancer les clients



Pour chaque joueur (4 terminaux différents) :

```bash

./sh13 <IP_serveur> <port_serveur> <IP_client> <port_client> <NomJoueur>

# Exemple :

./sh13 127.0.0.1 5000 127.0.0.1 6000 Joueur1

```

- Les ports clients doivent être distincts (6000,6001,6002,6003).

- Choisissez un nom unique pour chaque joueur.



---



## Comment jouer



1. **Connect** : chaque fenêtre, cliquez sur **Connect** pour rejoindre la partie.

2. **Distribution** : une fois 4 joueurs connectés, chacun reçoit 3 cartes (vignettes) et sa ligne de la grille se remplit.

3. **Tour par tour** : le bouton **GO** (vert) indique quel joueur peut jouer.



### Actions possibles (une par tour)

- **Enquête ouverte** : cliquez sur un symbole (rangée haute) puis **GO** ⇒ tous les joueurs lèvent la main (la grille se met à jour).

- **Enquête ciblée** : cliquez sur un nom de joueur (colonne gauche), puis un symbole, puis **GO** ⇒ seul le joueur ciblé révèle son nombre.

- **Accusation** : cliquez sur un nom de joueur (colonne gauche) sans symbole, puis **GO** ⇒ si juste, **victoire immédiate**, sinon élimination et la partie continue pour les autres.



---



## Structure du projet

```

PROJET/

├─ server.c         # Serveur TCP, gestion du jeu et des tours

├─ sh13.c           # Client SDL2, interface graphique et réseau

├─ Makefile         # Script de compilation

├─ cmd.sh           # Script pour compiler manuellement

├─ regle.pdf        # Règles du jeu (PDF)

├─ connectbutton.png # Bouton Connect

├─ gobutton.png     # Bouton Go

├─ sans.ttf         # Police de caractères

├─ SH13_0.png       # Vignettes personnages (0 à 12)

├─ SH13_ampoule_120x120.png  # Icônes symboles

├─ ...              # Autres icônes et images nécessaires

```



---



## Auteurs

- **Auteurs** : Wassim GHACHI, adaptation du concept « Sherlock Holmes »



---



