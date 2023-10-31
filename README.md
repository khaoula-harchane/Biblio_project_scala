# Biblio

Ce projet Scala consiste en la création d'une application de gestion de bibliothèque.

## Classes

### Livre

**Attributs:**
- `titre` : Chaîne de caractères
- `auteur` : Chaîne de caractères
- `annee de publication` : Numérique
- `estEmprunte` : Booléen (par défaut false, false indique que le livre n'est pas emprunté et est disponible dans la bibliothèque)

 **Méthodes:**
 - `emprunter` : change l'état d'un livre qui vient d'être emprunté à true
 - `rendre` :change l'état d'un livre qui était emprunté et vient d'être rendu à false

### Bibliotheque

**Attributs:**
- `listeDeLivres` : Liste de type Livre vide au début mais à laquelle on ajoutera des instances de la classe Livre
  
**Méthodes:**
- `ajouterLivre` : prend en paramètre un objet de type Livre qui sera ajouté à la liste listeDeLivres
- `rechercherParTitre`: prend en paramètre le titre de livre de type String, recherche le livre dans la liste par titre et 
renvoie une Option[Livre] qui peut avoir soit une valeur (Some) si le titre du livre est trouvé soit aucune valeur (None) s'il n'est pas retrouvé.
- `rechercherParAuteur`: même principe que la méthode `rechercherpartitre` sauf que la recherche se fait sur la base de l'auteur du livre
- `emprunterLivre`: cherche un livre par titre, tente de l'emprunter s'il n'est pas déjà emprunté, renvoie un succès, sinon signale une erreur si le livre est déjà emprunté ou introuvable. 
- `rendrelivre`: cherche un livre par titre, tente de le retourner s'il est emprunté, renvoie un succès, sinon signale une erreur si le livre n'est pas actuellement emprunté ou introuvable.
- `sauvegarderDansFichier`: prend un nom de fichier en paramètre et utilise PrintWriter pour écrire les données de la liste de livres dans ce fichier.
- `chargerDepuisFichier`: prend le fichier qui contient les données de la bibliothèque. Elle utilise getResourceAsStream pour obtenir un flux depuis le fichier dans les ressources de la classe. Ensuite, elle parcourt chaque ligne du fichier, crée un nouvel objet Livre avec les données de la ligne, et l'ajoute à la liste de livres à l'aide de la fonction `ajouterLivre`.

## Fichier de données mis à jour

Une fois le fichier sauvegardé après avoir lancé une opération donnée, les modifications seront visibles sur le fichier biblio.csv dont le path est target/scala-2.13/classes/biblio.csv et non le fichier biblio.csv de ressources.
<img width="693" alt="image" src="https://github.com/khaoula-harchane/Biblio_project_scala/assets/87319283/6e19fbb1-296b-4fbb-8f3f-746300803efc">

## Tests Unitaires

Nous avons réalisé des tests unitaires pour les deux méthodes clés `emprunterLivre` et `rendreLivre` tenant compte de plusieurs scénarios. Les test sont dans src/test/scala/BiblioTest.scala





