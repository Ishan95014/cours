1. Lancez Android Studio
2. Créez un nouveau projet via le + ou `Fichier > Nouveau > Projet`
	1. Choisissez “Empty activity”
![[images/Screenshot 2023-02-08 at 13.18.23.png]]
	2. Attention a bien sélectionner “Java” et non Kotlin comme langage.
![[images/Pasted image 20230208132203.png]]
3. On veut d’abord construire le layout de notre application, avec ses affichages et ses boutons. Dans le panneau de gauche exposant l’arborescence des fichiers, ouvrez donc dans `app > res > layout > activity_main.xml` 

4. Il y a en haut à droite trois options d’affichage pour les fichiers xml
![[images/Screenshot 2023-02-08 at 13.27.24.png]]
![[images/Pasted image 20230208132919.png]]
![[images/Pasted image 20230208132933.png]]

5. D’abord, supprimez l’élément texte “Hello World”, et ajoutez les éléments dont vous avez besoin par glisser-déposer de la palette vers l’écran blanc, 
![[images/Screenshot 2023-02-08 at 13.30.22 1.png]] 
![[images/Pasted image 20230208133516.png]]
6. Bon maintenant la partie avec un truc a comprendre : L’objectif est de designer une interface en définissant l’apparence des éléments seulement les uns par rapport aux autres, et par rapport à l’écran : *pas de valeurs en pixels !* Pour ça on va utiliser les *constraints*, les *layout_constraints* et *layout*.
	1. On séléctionne un élément
![[images/Pasted image 20230208134029.png]]

On clique sur un des “+” dans le Constraint widget pour ajouter une constraint
![[images/Pasted image 20230208134109.png]]

Une nouvelle constraint est ajoutée. 
![[images/Pasted image 20230208134122.png]]

Ensuite, mettez des constraints à zéro sur tous les éléments : Pour chaque élément, le constraint widget doit afficher 0 dans toutes les directions et la visualisation montrer les contraintes entre les éléments et entre les éléments et le bord.
![[images/Pasted image 20230208134524.png]]


Dans le panneau de droite, changez les *layout_width* et *layout_height* de tous les éléments de **wrap_content** à **0dp**.
![[images/Pasted image 20230208134756.png]]

wrap_content donne aux boutons la taille suffisante pour afficher leur contenu + un peu de padding, alors que 0dp prend toute la place disponible, étant donné les contraintes mises en place. 

Toujours dans le panneau de droite “Attributes”, cherchez “weight”
![[images/Screenshot 2023-02-08 at 13.49.45.png]]

Ce qui affiche les layout constraints : Personnellement je les ai tous mis à 1, sauf la layout constraint du bouton qui fera l’affichage couleur, que j’ai set à 2 pour qu’il soit 2 fois plus haut que les boutons.
![[images/Pasted image 20230208135106.png]]

Vous pouvez revenir sur les constraints et ajouter des marges et des gaps : 

![[images/Pasted image 20230208135331.png]]


Vous pouvez maintenant tester l’émulateur comme expliqué dans le TD : 
![[images/Pasted image 20230208135508.png]]


# Landscape

Layout 
clic droit
new
same name
dont save
dans la liste en bas a gauche orientation
fleche droite
landscape
save
