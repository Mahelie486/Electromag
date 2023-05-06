# Electromag
"""Le flux d’énergie
La section 2.4.4 du Griffiths présente une discussion sur le fait que l’énergie électrique se trouve emmagasinée dans le champ électrique. De même, la section 7.2.4 présente de façon similaire le fait que l’énergie magnétique est stockée dans le champ magnétique. Il est possible de caractériser le flux d’énergie électromagnétique grâce à une quantité nommée vecteur de Poynting et définie comme :
S = μ1 ( E × B ) . 0
Le vecteur de Poynting représente la quantité d’énergie par unité de temps par unité de surface transportée par les champs électromagnétiques. De par sa nature, ce vecteur est beaucoup utilisé avec les ondes électromagnétiques (il sera d’ailleurs vu plus en profondeur dans le cours Ondes Électromagnétiques donné à l’automne). Toutefois, l’expression pour S demeure valable dans toutes les situations. Pour plus de détails sur le vecteur de Poynting, veuillez consulter la section 8.1.2 du Griffiths.
Objectifs du travail
Le but de ce travail est calculer le flux d’énergie dans un circuit électrique simple. Le but est en fait d’illustrer numériquement que le transfert d’énergie entre une source et un élément de circuit se fait via les champs électriques et magnétiques. Ce concept non intuitif est illustré dans une vidéo de Veritasium. Ayant reçu plusieurs critiques (constructives), Veritasium a fait une seconde vidéo sur le même sujet.
Objectifs spécifiques
Pour réaliser ce travail vous devrez utiliser une base de code en Python pour laquelle certaines fonctions importantes en lien avec la physique électromagnétique sont manquantes.
1. Obtenir l’expression de la solution de l’équation de Laplace discrétisée en coordonnées carté- siennes en considérant le cas général ∆x ̸= ∆y.
2. Obtenir l’expression de la solution de l’équation de Laplace discrétisée en coordonnées polaires (cylindriques 2D) en considérant le cas général ∆r ̸= ∆φ.
3. Télécharger ou cloner le code de ce répertoire. Prenez le temps de regarder la structure du code et le rôle de chacun des modules.
4. Compléter les fonctions manquantes, c’est-à-dire celles qui retournent une erreur de type NotImplementedError. Utiliser numpy pour accélérer la vitesse des calculs.
• Solution de l’équation de Laplace pour le potentiel par la méthode de la relaxation, soit les fonctions :
— LaplaceEquationSolver._solve_in_cartesian_coordinate
— LaplaceEquationSolver._solve_in_polar_coordinate
• Calcul du champ magnétique par l’équation de Biot-Savart, soit les fonctions : — BiotSavartEquationSolver._solve_in_cartesian_coordinate
— BiotSavartEquationSolver._solve_in_polar_coordinate
• Calcul des champs (potentiel, champs électriques, magnétiques, Poynting) en tous points, soit la fonction :
— World.compute
5. Utiliser votre code pour calculer le flux d’énergie pour les situations présentées à la Figure 1. Les circuits 1a, 1b et 1c doivent être simulés en coordonnées cartésiennes et le circuit 1d doit être simulé en coordonnées cartésiennes et polaires.
Notes :
• La notation (r, φ) est utilisée en classe pour les coordonnées polaires. Toutefois, le code utilise plutôt la notation (r, θ). On pose donc ici que φ et θ représente le même angle, soit l’angle azimutal.
• Une discrétisation de 1 m est utilisée dans le code, soit ∆x = ∆y = ∆r = 1 m. Pour ce qui
est de ∆θ (ou ∆φ), la discrétisation sera variable en fonction de la taille N × M de la grille
représentant le monde tel que ∆θ = π rad. 2M
• Pour chacune de ces situations, vous devriez être en mesure d’illustrer que le flux d’énergie va de la source de tension aux résistances, peu importe la configuration du circuit.
"""
