# hello_world
Test repository for Jenkins Training session

### Etape 1 : 
Se creer un compte GitHub

### Etape 2 : 
Faire un Fork de ce repository

### Etape 3 (Facultatif) :
Cloner votre repo sur votre poste, puis verifiez que vous pouvez le compiler avec maven
`mvn compile`

### Etape 4 :
Creez une clé ssh sur votre poste avec la commande ssh-keygen

### Etape 5 :
L'enregistrer sur votre compte github et lui donner les droits de cloner votre repo

### Etape 6 :
Configurer un Job Freestyle, a partir de l'addresse de votre repo, qui compile, teste et stocke les artefacts de ce projet.

### Etape 7 :
Configurer Github pour qu'il envoye un Webhook a votre serveur et déclenche le build.
Si vous ne pouvez pas rendre votre serveur accessible de l'extérieur, utilisez le perioding polling de Jenkins a la place.

### Etape 8 :
Faites un commit qui casse un test ou la compilation, pushez et verifiez que tout fonctionne.




Il est fortement conseillé d'effectuer des test tout au long de la procedure.
