---
cssclass: img-grid
---

#tutorial 
# Intro
[[Stable Diffusion]] est une méthode de génération d’images à partir de texte. Elle est [[open source]] et développée par l’entreprise [[Stability.ai]]. On peut utiliser Stable Diffusion via le site de Stability, comme un service en ligne payant, comme Dall-E. Comme c’est open source, on peut également l’utiliser sur sa propre machine. 

# Les Modèles
Stability produit un modèle, un fichier au format .ckpt, qui contient les poids du modèle de génération d’images. Pour l’utilisateur, le modèle est la base du système, ce qui va fondamentalement déterminer les résultats. Il y a eu deux grandes versions de ce modèle, SD-v-1.4 et SD-v-1.5. 1.5 a apporté des améliorations de fond, notamment aux visages. 
NovelAI, une autre entreprise, (d’IA d’aide à l’écriture d’histoires) a custom train une variation du modèle de Stability, qui a des résultats en dessin, digital art et anime style bien meilleurs que le modèle SD standard. Il a depuis été leaked et peut être utilisé en lieu de SD. Ils ont modifié le modèle d’origine. On l’appelle “novelAi model”, personnellement je l’ai enregistré sous *novel.ckpt*.
Comme chacun peut entrainer son propre modèle, (via Dreambooth, mais pas seulement) beaucoup de modèles sont disponibles en ligne. Attention, il faut les unpickle (possible vecteur de virus).

# Les fonctionnalités de base
### txt2img 
Prend un prompt, un texte descriptif, et ressort une image. 
- On peut spécifier une *résolution*, (en hauteur et largeur), ce qui permet de faire des images plus ou moins grandes, avec un ratio plus ou moins carré ou rectangulaire, 
- Le nombre de *steps*, c'est-à-dire le nombre d’itérations pendant lesquelles le système va tourner (le nombre de steps influe sur les détails : plus de steps permet au système d’augmenter les détails de plus en plus petits sur l’image). 
- La *cfg scale*, qui donne plus ou moins de latitude au modèle pour coller plus ou moins à notre prompt. 
- Le *sampler*, compliqué, utilisez le premier activé par défaut, ou alors, testez les tous à la fois avec scripts > x/y > sur x choisir “samplers” et recopier leurs noms séparés par des virgules, rien sur y, > run.

### img2img
Fonctionne exactement de la même manière que txt2img, sauf qu’au lieu d’utiliser une image purement composée de bruit comme image de départ, on peut fournir sa propre image. Un curseur important dans ce mode est *[[denoising]]* : une valeur faible produira une image proche de l’originale, une valeur élevée produira quelque chose de complètement différent.  

### inpainting
Une fois qu’on a une image qui ressemble à ce que l’on veut, on peut en demander des variations : on peut reprendre le *seed* de cette image et générer plusieurs variations utilisant ce même seed. Mais il se peut que les erreurs soient localisées : souvent les yeux et les mains. Dans ce cas, il vaut mieux utiliser l’*inpainting* : on efface les zones de l’image ratée, et on réécrit un prompt uniquement pour ces zones. On peut *inpaint at full resolution*, c'est-à-dire utiliser la résolution totale choisie pour générer cette petite section de l’image.

# Dreambooth
Dreambooth est une technique développée par des googlers qui a plusieurs implémentations. Elle permet de continuer à train un modèle sur un petit set d’images d’un sujet précis. Un style de dessin ou de photographie, un objet, un animal ou un visage en particulier, par exemple. On peut générer un modèle custom avec son visage dans dreambooth. 

# Les UIs
SD est utilisable en ligne, sur le site de Stability, comme un service payant. Mais étant open source, il y a aussi des GUIs installables. Il y a des applications, mais la version la plus répandue, la plus aimée est celle du développeur AUTOMATIC1111. C’est une webUI, soit une installation qui whip up un serveur web local, on interagit ensuite avec SD via une page web locale. 

# Les fonctionnalités additionnelles
Les UIs comme celle de AUTOMATIC1111 incluent beaucoup de fonctionnalités qui sont venues se greffer à SD. Elles sont plus ou moins intégrées au système. Par exemple, il y a plusieurs modèles d’upscaling disponible, pour scale 2-8x les images générées avec SD. Système complètement indépendant, mais bien intégré dans l’UI. Il y a aussi des plugins pour améliorer les visages dans les images générées, etc. 

# & much more ! 
- les VAE, 
- les Hyperviseurs, 
- mixer des checkpoints, 
- les poids des termes dans les prompts, 
- les tags danbooru, 
- les tests d’influence des noms d’artistes, de courants artistiques, de style d’image, 
- la ponctuation d’accentuation, 
- et caetera

# Utiliser Google Colab
Google Colab est un service de google qui permet aux chercheurs d’utiliser une version propriétaire des [[Jupyter Notebook|Jupyter Notebooks]], les Colab Notebooks, avec du hardware puissant sur leur backend (GPU ou TPU). 

![[Pasted image 20221116201922.png]]

Un Notebook est un fichier au format .ipynb, pour colab et pour jupyter. Dans google Colab ils sont stockés sur google drive. 

Sur la gauche, le bouton fichier permet de naviguer l’arborescence de fichiers. Cet espace est créé avec une session colab, et est détruit en même temps. Beaucoup de noteboooks ajountent une connexion a un google drive pour y sauvegarder des fichiers. 

Au millieu de la page, les notebooks sont constitués de *cellules* qui peuvent contenir du code ou du markdown. Le code peut être lancé avec le bouton play qui apparait on::hover. Chaque cellule peut être lancée indépendamment. 

Dans sa version gratuite, Google limite l’usage a quelques heures par jour, et le gpu à un modèle moyen. (Une Nvidia T4). Il faut interragir avec la page même pendant les longs moments de run pour ne pas se faire kick. 

# Utiliser Vast.ai
Pareil mais :
- faut changer plein de trucs dans les fichiers pour les rendre compatibles avec vanilla jupyter
- c’est payant
- ça permet d’utiliser des GPU très puissants et de ne pas se faire random déconnecter

# Utilisation de AUTOMATIC1111
AUTOMATIC1111 est le nom du développeur qui fait la meilleure implémentation de Stable Diffusion, et par conséquent le nom couramment utilisé pour désigner son implémentation. On utilisera ici un fork optimisé. Il a un downside : il a besoin de fichiers d’optimisation pour chaque GPU différent sur lesquels il peut run, et pour l’instant les GPUs disponibles sur Fast.ai n’en font pas partie donc on ne peut pas l’y utiliser. Sur colab ça marche bien. 

### 1. Vérifier son espace disponible Google Drive
![[Pasted image 20221116203551.png]]
Il y a besoin d'au moins 5gb de libre sur google drive.

### 2. Créer un compte sur huggingface.co

### 3. Obtenir l’accès au modèle
Allez à l’adresse suivante et acceptez les conditions :
https://huggingface.co/runwayml/stable-diffusion-v1-5

#### 4. Obtenir un token huggingface
Allez à https://huggingface.co/settings/tokens, faites new token et copiez le.

### 5. Ouvrir le notebook sur colab
Suffit de cliquer sur le lien : 
https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb#scrollTo=CFWtw-6EPrKi

### 6. Ajouter le token. 
Pour pouvoir télécharger le modèle SD 1.5 depuis huggingface, collez votre token dans la zone de texte de la troisième code box. 

### 7. Exécuter le code
![[Pasted image 20221116204446.png]]

Autorisez la connexion à gdrive. 

Faites Exécution > tout exécuter. Ca va prendre quelques minutes. Restez sur la page, interragissez avec, pour ne pas vous faire kick. 

### 8. Lancer la webUI
![[Screenshot 2022-11-16 at 20.46.03.png]]
A la fin, votre webUI sera live à une addresse générée aléatoirement. Ouvrez-là dans un nouvel onglet.

### 9. Utiliser la webUI
Voir la section “fonctionnalités de base”. 

### Bonus : Utiliser des modèles custom
##### 1. Ajouter les modèles
Uploadez vos modèles au format .ckpt sur google drive, de préférence dans 
sd > stable-diffusion-webui > models > stable-diffusion 
“sd” se trouvant à la racine de  gdrive si vous avez déjà utilisé le colab. 
![[Pasted image 20221116205812.png]]

##### 2. Spécifier le chemin du modèle dans le colab
Au lieu de tout exécuter d’un coup, lancez seulement les deux premières code boxes.
![[Pasted image 20221116205108.png]]

Avec le navigateur dans la section de gauche, naviguez à votre fichier .ckpt, cliquez les trois points, **(1)**, puis copiez son chemin d’accès **(2)**, et collez-le dans la section “Path_to_trained_model”.
![[Screenshot 2022-11-16 at 20.53.32.png]]

Ça doit ressembler à ça : 
![[Pasted image 20221116205520.png]]

Lancez la troisième code box et les suivantes comme précédemment.

# Utilisation de Dreambooth

# Utiliser SD’s Web UI 

![[Pasted image 20221116212210.png]]

Si plusieurs modèles sont dans le dossier modèles, on peut changer celui en cours d’utilisation via le menu en haut à gauche. 
![[Pasted image 20221116212247.png]]

![[Pasted image 20221116213452.png]]


On peut tester l’influence de variables une ou deux à la fois avec le script x/y, exemple d’utilisation : 
![[Pasted image 20221116213508.png]]
Ce script permet de générer une grille d’images en changeant pour chacune le sampler utilisé. 


# Les modèles d’anime
NovelAI, Waifu Diffusion, et AnythingV3 pour ne citer qu’eux sont des modèles entrainés, entre autres, sur la bibliothèque d’images danbooru. 
Ils se loadent comme n’importe quel autre modèle. Ils sont 


# Tests : 
drawig to realistic : 
1. img2img
2. loopback script
3. anime,cartoon,hentai,drawing in the neg prompt 