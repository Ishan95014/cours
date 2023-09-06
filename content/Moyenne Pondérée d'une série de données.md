# Moyenne Pondérée

Quand on *calcule une [[Moyenne d'une série de données|Moyenne]]*, on peut décider que chaque nombre dans l’ensemble de nombres qu’on considère n’a *pas la même valeur*. On va alors calculer une moyenne *pondérée*.

Typiquement, quand on calcule la moyenne générale d’un élève, on considère que la note de chaque matière n’a *pas la même valeur*. 
Ou alors à l’intérieur d’une matière, on considère qu’un QCM de quelques minutes n’a *pas la même importance* qu’un gros devoir d’une heure. 

Si on reprend les valeurs de la fiche [[Moyenne d'une série de données|Moyenne]] : 

| Maths | Français | Physique | Histoire |
|-------|----------|----------|----------|
| 20    | 19       | 17       | 18       |

Ici on décide de *pondérer*, c’est à dire de donner un *poids*, une *importance* différente à chaque note. 
On calcule donc une *moyenne générale pondérée*. 

Ici on décide que le 
- les maths valent $2$, (donc 2x plus important que la normale),
- français vaut $1$, 
- la physique $3$, et 
- l’histoire $2.5$

1. On ajoutera devant chaque note son *coefficient*, on multipliera la note par son coefficient.
			$(2*20)+(1*19)+(3*17)+(2.5*18) = 155$ ← *somme pondérée des moyennes*
			(Les parenthèses sont pour la lisibilité)
			
2. Qu’on divise par le *nombre de notes*. Ici comme des notes comptent plusieurs fois il faut diviser par la *somme des coefficients*.
			$2+1+3+2.5 = 8.5$ ← *somme des coefficients*
			
3. On divise la *somme pondérée des moyennes* par la *somme des coefficients*
			$155/8.5 = 18.24$ ([[valeur arrondie]])

###### La moyenne pondérée est de $18.24$
-----
En écriture mathématique :
##### $$ \bar{x} = \frac{(n_1×x_1) + (n_2×x_2) + ... + (n_n×x_n)}{n_1+n_2+...+n_n} $$
###### Explication : 
La moyenne notée $\bar{x}$ est égale a la somme $x_1 + x_2 + ... + x_n$ de toutes les valeurs, de la première valeur à la $n$-ième valeur divisée par le nombre de valeurs, $n$.


#math 