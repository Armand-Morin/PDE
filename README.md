# PDE
partial differential equation

Le projet consiste à étudier l'écoulement d'un fluide (de l'eau, mais ça peut aussi être de l'huile dans un vérin ou un autre fluide) dans un tuyau contenant un cylindre. Cette modélisation est donc basée sur l'étude des équations de Navier Stokes.
On considère les équations générales incompressibles de Navier-Stokes sur un domaine $\Omega \subset \mathbb{R} ^2$, consistant en une paire d'équations ou $ u $ correspond à la vitesse du fluide et $ p$  à la pression:

\begin{cases}
\rho\frac{\partial u}{\partial t}  + u \nabla u - \nu\Delta  u + \nabla p = 0  \\
\nabla u =0 \\
\end{cases}
 
Avec le paramètre $ \nu $ est la viscosité dynamique.


Ce problème combine plusieurs défis car dans les équations, nous avons une dépendance temporelle de plus elles sont non-linéaires et les variables sont à valeurs vectorielles. De plus il y a deux inconnues que l'on cherche : la vitesse et la pression.


Dans notre cas, le modèle on peut se réécrire de la manière suivante :
\begin{cases}
\rho(\frac{\partial u}{\partial t}  + (u \cdot \nabla) u) = \nu\nabla  \sigma(u,p) + f   \\
\nabla u =0 \\
\end{cases}
 
Du côté droit f est une force donnée exprimée par unité de volume, $ σ( u , p ) $ désigne le tenseur des contraintes, qui pour un fluide newtonien est donné par:
$ σ( u , p ) = 2 μ ϵ ( u ) - p I $

et où $ ϵ ( u ) $  est le tenseur de la vitesse de déformation suivant:
$ ϵ ( u ) =1/2( ∇ u + ( ∇ u)^T) $


# Résultats :
Les photos suivantes ont été obtenues pour une valeur de $ \mu=0.001$.

Ce sont les résultats que j'ai obtenu en prenant un cylindre au milieu du canal d'écoulement de l'eau. On aurait pu prendre une autre forme géometrique pour observer son impact sur l'évolution du flux d'eau.

On remarque qu'il y a apparition d'oscillations et que le fluide devient turbulent à la sortie du canal.  
Par ailleurs derrière le cylindre on peut remarque qu'il y a des vortex (Tourbillon qui se produit dans la fluide). Ces derniers sont à éviter car ils ralentissent considérablement la vitesse d'écoulement dans le tube 

![vitesse+pression100](https://user-images.githubusercontent.com/72650161/113295401-72c52700-92f8-11eb-8580-89387b4eb642.png)
![vitesse+pression500](https://user-images.githubusercontent.com/72650161/113295419-78227180-92f8-11eb-818b-44c664d4e07d.png)
![vitesse+pression700](https://user-images.githubusercontent.com/72650161/113295433-7c4e8f00-92f8-11eb-97a8-2d7b719bf41f.png)
![vitesse+pression1200](https://user-images.githubusercontent.com/72650161/113295481-8b354180-92f8-11eb-820d-29be89d58e9e.png)
![vitesse+pression1500](https://user-images.githubusercontent.com/72650161/113295488-8ec8c880-92f8-11eb-9aee-88b5e974bb8f.png)
![vitesse+pression2500](https://user-images.githubusercontent.com/72650161/113295497-912b2280-92f8-11eb-8de1-421a21a52233.png)
![vitesse+pression2100](https://user-images.githubusercontent.com/72650161/113295492-8ff9f580-92f8-11eb-9cbe-449fc3c05756.png)
![vitesse+pression4980](https://user-images.githubusercontent.com/72650161/113295502-925c4f80-92f8-11eb-8009-856045c3c6f3.png)

# $\mu=0.005$
D'autres simulation avec un coefficient $\mu=0.005$ conduisent aux résultats suivants:
![vitesse+mu3200](https://user-images.githubusercontent.com/72650161/113295688-cf284680-92f8-11eb-8939-5027b138bcee.png)
On remarque une sorte de "trainée" plus longue derrière le cylindre.


# $\mu=0.0005$
Cette simulation est effectuée pour $\mu=0.0005$.
On remarque qu'il a moins de turbulence et que l'écoulement est plus laminaire après le passage du cylindre. On en déduit que ce coefficient a une influence sur l'écoulement.
![vitesse+mu4980](https://user-images.githubusercontent.com/72650161/113295876-08f94d00-92f9-11eb-8987-90eade2f5574.png)


## Bibliographie et références
La référence que j'ai utilisé pour me servir de sujet est:
- [DFG flow around cylinder](http://www.featflow.de/en/benchmarks/cfdbenchmarking/flow/dfg_benchmark2_re100.html)

Le site Fenics pour la documentation des fonctions, les exemples et tutoriels :
- [fenics Project](https://fenicsproject.org)


# Annexe
Différents résultat :
Lors de la simulation, j'ai obtenu des résultats comme ci-dessous lors que j'utilisais des fonctions linéaires par morceau comme espace de définition de V. Mais aussi lorsque j'utilisais des pas de temps trop grand les valeurs divergeaient aussi.


![image_6](https://user-images.githubusercontent.com/72650161/113296007-35ad6480-92f9-11eb-93ee-507d5eb5296b.png)
