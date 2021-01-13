# TP Linux

## 1. Installation Linux ou VM

## 2. CLI

### Références

- Documents issus de vo propres recherches sur Internet
- Si vous le souhaitez, le [document compagnon du MOOC « Maîtriser le shell Bash »](www.opimedia.be/DS/languages/Bash/MOOC-Maitriser-le-shell-Bash--Document-compagnon--v2-6-2019.pdf), en français et relativement bien fait

### Les commandes à considérer

`pwd, cd, ls, file, less, head, tail, mkdir, cp, mv, rm, rmdir, touch, echo, set, unset, export, env, alias, history, nl, find, grep, sed`

### Les fonctionnalités du shell à considérer

- « Globbing » de fichier
- Variables Shell
- Variables d'environnement (commandes `export` et `env`)
- Alias de commandes (commande `alias`)
- Historique de commandes
- Redirection d'entrées/sorties (STDOUT, STDERR, STDIN, utilisations des caractères `<` et `>` dans les commandes)
- « Piping » (caractère `|` dans les commandes, bien comprendre différence avec `>`)
- Sous-commandes (`$(commande a executer)` à l'intérieur d'une autre commande)
- Expressions régulières
- Bien comprendre `find` (recherche fichiers) et `grep` (recherche dans fichiers)
- Commande `sed` pour éditer un fichier en ligne de commande (automatiquement), par exemple pour remplacer une chaîne de caractère par une autre
- Commandes d'archivage et de compression : `tar`, `gzip`, `gunzip` `bz2`, `xz`

### 1. Gestion de fichiers

1. Ouvrir un terminal
2. Afficher le répertoire courant
3. En utilisant un chemin absolu, aller sur le répertoire `/etc`
4. En utilisant un chemin relatif, aller sur le répertoire `/etc/skel`
5. En utilisant un chemin relatif, remonter sur `etc`
6. Afficher les fichiers du répertoire courant
7. Même chose en « affichage détaillé »
8. Afficher tous les fichiers du répertoire courant qui commencent par `s`
9. Lancer la commande qui permet de déterminer le type de contenu dans le fichier `/etc/group`
10. Afficher les cinq dernières lignes du fichier `/etc/group`
11. Exécuter la commande qui revient directement à votre répertoire personnel
12. Créer un répertoire nommé `temp` dans votre répertoire personnel
13. Copier le fichier `/etc/passwd` dans le répertoire `temp`
14. Copier le répertoire `/etc/ppp` dans le répertoire courant (ignorer toutes les erreurs "permission denied")
15. Renommer le répertoire `ppp` du répertoire courant en `peers`
16. Mettre à jour le timestamp du fichier `temp/passwd` à la date et heure courantes
17. Créer un nouveau fichier vide nommé `test` dans le répertoire `temp`
18. Supprimer le fichier `temp/passwd`
19. Supprimer le répertoire `peers`

### 2. Quelques fonctionnalités du Shell

1. Afficher le contenu de la variable `HOME`
2. Afficher toutes les variables shell avec leur contenu
3. Afficher le contenu de la variable `TEST` (noter que cette variable n'a en fait aucun contenu actuellement)
4. Changer le shell courant afin qu'un message d'erreur s'affiche quand une variable indéfinie est utilisée
5. Modifier la variable `PATH` pour ajouter le répertoire `/opt`
6. Créer une variable d'environnement appelée `EVENT` et lui donner la valeur "maintenant" en utilisant une seule commande
7. Afficher toutes les variables d'environnement
8. Créer un alias dans le shell courant pour la commande `ls` de telle sorte que ça lance la commande `ls -a`
9. Afficher tous les alias du shell courant
10. Supprimer l'alias `fgrep` du shell courant
11. Afficher une liste des commandes précédemment exécutées
12. Re-exécuter la dernière commande `ls` de l'historique
13. Changer le nombre maximum de commandes stockées dans l'historique du shell courant (2000)
14. Exécuter la commande `ps -ef` et utiliser un *pipe* pour passer la sortie à la commande `less`
15. Afficher tous les fichiers dans la structure du répertoire `etc` (sous-répertoires inclus) qui dont le groupe propriétaire est le groupe `lp`
16. Afficher tous les lignes dans le fichier `etc/passwd` qui contiennent au moins trois nombres d'affilé
17. Afficher le fichier `etc/passwd` avec toutes les occurrences de `root` remplacées par `XXXX`

### 3. Compression

1. En utilisant l'option « verbose », créer un fichier tar appelé `etcppp.tar` qui contient le contenu du répertoire `etc/ppp` (ignorer les messages d'erreurs potentiels)
2. Afficher le contenu de l'archive `etcppp.tar` (sans l'extraire)
3. Créer un répertoire `extraction-tar` dans le répertoire courant
4. Extraire le contenu de l'archive `etcppp.tar` dans le répertoire `extraction-tar`
5. Compresser l'archive `etcppp.tar` en utilisant la commande `gzip`, sans écraser le fichier `etcppp.tar` ; le fichier résultant devra se nommer `etcppp.tar.gz`
6. Compresser l'archive `etcppp.tar` en utilisant la commande `bzip2`, sans écraser ; le fichier résultant devra se nommer `etcppp.tar.bz2`
7. Comparer les tailles des deux fichiers compressés (`.gzip` et `.bz2`) ; lequel des deux algorithmes semble avoir un meilleur taux de compression ?
8. Supprimer le fichier `etcppp.tar`
9. Décompresser le fichier `etcppp.tar.gz`
