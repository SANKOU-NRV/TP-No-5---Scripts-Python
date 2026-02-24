# TP-No - 5 - Scripts-Python

**Automatisation des taches d’administration**
    
  SILLAH Sankou
  24/02/2026

**EXERCICE 1 - Introduction `a Python**

***1) Lire les sections I à III du cours***

Les sections I à III servent généralement à comprendre l’interpréteur, les types simples (nombres, chaînes), et la syntaxe de base.

***2) Lancer l’interpréteur et effectuer les calculs suivants, et interpréter/expliquer chaque résultat***

*Explication* : Python calcule directement en mode interactif. Les entiers peuvent être très grands sans “overflow” classique.
Les chaînes se concatènent avec + et se répètent avec * 

```code
sankou@p20221:~$ mkdir TP5
sankou@p20221:~$ cd TP5
sankou@p20221:~/TP5$ python3
Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 24*7
168
>>> (3+2)*-4
-20
>>> 2**8
256
>>> 2**1000-1
10715086071862673209484250490600018105614048117055336074437503883703510511249361224931983788156958581275946729175531468251871452856923140435984577574698574803934567774824230985421074605062371141877954182153046474983581941267398767559165543946077062914571196477686542167660429831652624386837205668069375
>>> 'IUT' + 'de Villtaneuse'
'IUTde Villtaneuse'
>>> 3*'ALLO'
'ALLOALLOALLO'
>>> 
```
ici : 
**24*7** fait une multiplication entière

**(3+2) * -4** calcule d’abord la parenthèse puis multiplie par un nombre négatif

** est une puissance

2**1000 - 1 est un entier très grand (Python gère les grands entiers)

**+** concatène les chaînes

**3 * 'ALLO '** répète la chaîne 3 fois

***3) Saisir le code suivant dans un fichier essai.py, l’enregistrer et lancer son execution :***

*Explication* : La première ligne (shebang) indique quel interpréteur utiliser. (voir essai.py)
L’encodage UTF-8 évite les soucis avec les accents. print() affiche simplement le texte à l’écran.

```code
sankou@p20221:~/TP5$ nano essai.py
sankou@p20221:~/TP5$ chmod +x essai.py
sankou@p20221:~/TP5$ ./essai.py
Bonjour !
```

***4) Lire les sections IV et V du cours, que fait le code suivant?***

*Le code en question ci dessous :*

```code
#! / u s r / b i n / env python
# −∗− c o d i n g : u t f −8 −∗−
i = 0
for x in [ ’ bo nj o ur ’ , ’ l e s ’ , ’ e n f a n t s ’ ] :
i = i + 1
print s t r ( i ) + ’ ’ + x
```
*Explication* : ici la boucle for parcourt la liste élément par élément.
i sert à numéroter les éléments affichés.
str(i) convertit l’entier en chaîne pour l’affichage.

*Resultat* : 

```code
sankou@p20221:~/TP5$ nano code2.py
sankou@p20221:~/TP5$ chmod +x code2.py
sankou@p20221:~/TP5$ ./code2.py
1 bonjour
2 les
3 enfants
```

***5) des fonctions supplémentaires sont accessibles via des modules qu’il faut « importer » :
import math
print math . s q r t ( 1 0 )
Le module os d´efinit de nombreuses fonctions utiles pour manipuler des fichiers et
acceder au systeme d’exploitation. Par exemple, os.listdir( rep ) rend une liste des
noms de fichiers et repertoires presents dans le repertoire indique 
(comme le fait la commande UNIX ls).
A l’aide de os.listdir, ´ecrire un script qui affiche la liste des fichiers dans le r´epertoire
/tmp.***

*Explication* : os.listdir() renvoie la liste des noms présents dans un dossier.
Ici on parcourt /tmp et on affiche chaque entrée. C’est l’équivalent Python d’un ls simple.(voir code liste_tmp.py)

*Resultat :*

```code
sankou@p20221:~/TP5$ nano liste_tmp.py
sankou@p20221:~/TP5$ chmod +x liste_tmp.py
sankou@p20221:~/TP5$ ./liste_tmp.py
systemd-private-9465980ecbc44769a4220bf997853a97-systemd-logind.service-15SOFf
systemd-private-9465980ecbc44769a4220bf997853a97-apache2.service-uYeWZi
Temp-880356d2-a152-4ae2-9169-6c5f02465f9e
.font-unix
systemd-private-9465980ecbc44769a4220bf997853a97-upower.service-wSOhzh
VeyonCLI.log
.Test-unix
VeyonServer.log
tmpaddon
dbus-HcumWo2FxW
.ICE-unix
.xfsm-ICE-8PX8K3
runtime-root
.X11-unix
tmp.24BZW3rWfK
.X0-lock
VeyonServiceDataManager
tmpaddon-1
VeyonFeatureWorker-8e997d84-ebb9-430f-8f72-d45d9821963d.log
systemd-private-9465980ecbc44769a4220bf997853a97-colord.service-Km9z7g
ssh-stGvXmZGG0QQ
systemd-private-9465980ecbc44769a4220bf997853a97-ModemManager.service-Kju98g
VeyonService.log
systemd-private-9465980ecbc44769a4220bf997853a97-systemd-timesyncd.service-x3btYh
.XIM-unix
```
***6) Comment accéder à un argument de la ligne de commande dans un script Python ?
(autrement dit, quel est l’´equivalent de $1, $2, ...)***

*Explication :*

En Python, les arguments sont dans sys.argv (liste). sys.argv[0] est le nom du script, sys.argv[1] le premier argument, etc.
sys.argv joue le rôle des $1, $2 en shell. On vérifie souvent la longueur avant d’accéder à un indice.
Ça rend le script réutilisable avec différents paramètres.

***7) Modifiez votre script pour qu’il affiche les fichiers situ´es dans le r´epertoire indiqu´e
sur la ligne de commande.***

*Resultat :*
```code
sankou@p20221:~/TP5$ nano liste_arg.py
sankou@p20221:~/TP5$ chmod +x liste_arg.py
sankou@p20221:~/TP5$ ./liste_arg.py
Usage: ./list_dir.py <repertoire>
sankou@p20221:~/TP5$ 
```

*Explication :* Ici je récupère le nom du répertoire depuis la ligne de commande avec sys.argv.
Je vérifie qu’un seul argument est bien donné sinon j’affiche un message d’erreur.
Ensuite j’utilise os.listdir() pour afficher son contenu.
Je gère aussi les erreurs possibles pour éviter que le script plante.


***8) Que fait la fonction os.system() ?***

*Explication :* La fonction os.system() permet d’exécuter une commande du système comme si je la tapais dans le terminal.
Quand j’utilise os.system("ls"), Python lance la commande dans un sous-shell. La commande s’exécute et s’affiche directement dans le terminal.
La fonction me renvoie seulement le code de retour (0 si tout s’est bien passé). Je ne récupère pas facilement le texte produit par la commande.

***9) Que fait la fonction os.popen() ? En quoi os.popen(’ls’) est-il diff´erent de
os.system(’ls’) ?***

*Explication :* La fonction os.popen() permet d’exécuter une commande système et de récupérer sa sortie.
Avec os.popen("ls"), je peux lire le résultat de la commande dans une variable.
Contrairement à os.system("ls"), je peux traiter le texte en Python.
os.system() affiche seulement le résultat mais ne me permet pas de le manipuler.
Donc os.popen() est plus utile si je veux exploiter la sortie dans mon script.

**EXERCICE 2 - Tri**

Les fonctions open(filename) ou os.popen(command) ram`enent un objet « fichier ».
La méthode readlines() sur les objets fichiers permet de lire en une fois toutes les
lignes du fichier (texte). Elle rend une liste de chaˆıne de caract`eres.
Ecrire un script Python (tri.py) qui affiche le contenu d’un fichier (dont le nom sera
spécifié sur la ligne de commande) avec les lignes tri´ees par ordre alphanum´erique. Vous
realiserez deux versions diff´erentes du script :

***1) la première utilisant os.popen() et la commande Unix sort***

*Résultat :*

```code
sankou@p20221:~/TP5$ nano tri_popen.py
sankou@p20221:~/TP5$ chmod +x tri_popen.py
sankou@p20221:~/TP5$ ./tri_popen.py
Usage: ./tri_popen.py <fichier>
sankou@p20221:~/TP5$ 
```

*Explication :* Dans cette version, je laisse le système faire le tri avec la commande Unix sort.
J’utilise os.popen() pour exécuter la commande et lire son résultat.
Ensuite j’affiche chaque ligne triée dans le terminal.
Donc ici Python sert surtout d’intermédiaire pour lancer la commande système. (voir code tri_popen.py)


***2) la seconde version utilisant la methode Python sort() sur une liste de chaınes de
caracteres***

*Résultat :*

```code
sankou@p20221:~/TP5$ nano tri_python.py
sankou@p20221:~/TP5$ chmod +x tri_python.py
sankou@p20221:~/TP5$ ./tri_python.py fichier.txt

betis
chelsea 
malmo
sankou
sillah

```

*Explication :* Dans cette version, je fais le tri directement en Python.
Je lis toutes les lignes du fichier dans une liste avec readlines().
J’utilise ensuite la méthode sort() pour trier la liste.
Ici tout le traitement est fait en Python sans utiliser de commande externe.
(voir code tri_python.py)


**EXERCICE 3**

*Explication :* Ici je crée moi-même un fichier CSV pour tester mon script.
Il contient des nombres et des cases vides pour vérifier les statistiques.
Comme ça je peux voir si mon programme calcule bien les min, max et moyennes.
Ça me permet de vérifier que tout fonctionne correctement avant de rendre le TP.

*Résultat :*

```code
sankou@p20221:~/TP5$ nano exemple.csv
sankou@p20221:~/TP5$ nano csv_stats.py
sankou@p20221:~/TP5$ chmod +x csv_stats.py
sankou@p20221:~/TP5$ ./csv_stats.py exemple.csv
*** Informations sur la colonne Nom
Nombre de lignes: 5
Nombre de valeurs manquantes: 0
statistiques non disponibles
Nombre de valeurs distinctes: 5

*** Informations sur la colonne Age
Nombre de lignes: 5
Nombre de valeurs manquantes: 0
Min=19.000000, Max=32.000000, Moyenne=23.8000
Nombre de valeurs distinctes: 4

*** Informations sur la colonne Note
Nombre de lignes: 5
Nombre de valeurs manquantes: 0
Min=6.000000, Max=15.000000, Moyenne=11.4000
Nombre de valeurs distinctes: 5
```

Pour la colonne Nom, il n’y a aucune valeur manquante et les statistiques numériques ne sont pas disponibles car il s’agit d’une colonne texte. Le script indique correctement qu’il y a 5 valeurs distinctes.
Pour la colonne Age, le programme a calculé le minimum, le maximum et la moyenne à partir des valeurs numériques présentes. Les résultats sont cohérents avec les données du fichier, ce qui montre que le traitement des nombres fonctionne correctement.
Pour la colonne Note, le script a également calculé les statistiques numériques sans erreur. Les valeurs affichées correspondent aux données du fichier, ce qui confirme que l’analyse des colonnes est bien réalisée.

*Explication du code Python* :

Dans ce script, je commence par lire le fichier CSV passé en argument.
Je sépare la première ligne pour récupérer les noms des colonnes, puis j’analyse les lignes suivantes une par une.
Je compte les valeurs manquantes, j’identifie les valeurs numériques pour calculer le minimum, le maximum et la moyenne, et j’utilise un set pour compter les valeurs distinctes.
Enfin, j’affiche les statistiques pour chaque colonne de manière structurée. (voir script csv_stats.py + exemple.csv)


**Conclusion**

Ce TP m’a permis de mettre en pratique les bases de Python appliquées à l’administration système.
J’ai appris à manipuler des fichiers, traiter des données structurées et gérer les erreurs proprement.
L’exercice sur le CSV m’a permis de comprendre comment analyser des données colonne par colonne.
Ce travail renforce ma capacité à automatiser des tâches d’analyse avec Python de manière claire et efficace.























