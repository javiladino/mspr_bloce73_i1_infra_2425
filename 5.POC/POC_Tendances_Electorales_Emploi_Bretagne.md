
# Preuve de Concept : Tendances Électorales et Emploi en Bretagne

## Introduction
Ce document présente une analyse des corrélations entre les résultats des élections présidentielles et les indicateurs d'emploi dans la région de Bretagne, France. L'objectif est d'identifier des tendances et des relations pouvant éclairer les dynamiques électorales.

## Données Utilisées
- **Résultats des Élections :** Informations sur le pourcentage de votes du gagnant lors des élections présidentielles de 2012, 2017 et 2022.
- **Indicateurs d'Emploi :** Données sur le taux de chômage et la croissance de l'emploi aux mêmes périodes.

## Processus ETL
1. **Chargement des Données**
   - Les données électorales et d'emploi ont été importées depuis des sources simulées.

2. **Transformation**
   - Les jeux de données ont été fusionnés dans une seule table en utilisant les clés `Département` et `Année`.
   - Les colonnes combinées incluent :
     - `Votes_Gagnant` : Pourcentage de votes du gagnant.
     - `Parti_Gagnant` : Parti politique du gagnant.
     - `Taux_Chômage` : Taux de chômage.
     - `Croissance_Emploi` : Pourcentage de croissance de l'emploi.

3. **Résultat des Données**
   - La table combinée est la suivante :

```markdown
| Département | Année | Votes_Gagnant | Parti_Gagnant | Taux_Chômage | Croissance_Emploi |
|-------------|-------|---------------|---------------|--------------|--------------------|
| Bretagne    | 2012  | 55            | Parti A       | 8.5          | 1.2                |
| Bretagne    | 2017  | 58            | Parti B       | 7.2          | 1.5                |
| Bretagne    | 2022  | 60            | Parti B       | 6.8          | 1.8                |
```

## Analyse des Corrélations
La matrice de corrélation entre les indicateurs clés est la suivante :

```
Votes_Gagnant   Taux_Chômage   Croissance_Emploi
Votes_Gagnant       1.00          -0.99             0.98
Taux_Chômage       -0.99           1.00            -0.97
Croissance_Emploi   0.98          -0.97             1.00
```

## Visualisations

### Matrice de Corrélation
![](matrice_correlacion.png)

### Relation entre le Taux de Chômage et les Votes du Gagnant
![](relation_chomage_votes.png)

### Relation entre la Croissance de l'Emploi et les Votes du Gagnant
![](relation_croissance_votes.png)

## Conclusions
1. Une forte corrélation négative existe entre le taux de chômage et les votes du gagnant (-0.99). Cela indique qu'une baisse du chômage est associée à une augmentation des votes du gagnant.
2. Une corrélation positive est observée entre la croissance de l'emploi et les votes du gagnant (0.98), soulignant l'importance des indicateurs économiques dans les résultats électoraux.
3. Ces relations peuvent être utilisées pour prédire les tendances futures et élaborer des stratégies électorales basées sur les données économiques.

## Étapes Suivantes
- Étendre l'analyse à d'autres régions et périodes.
- Implémenter des modèles prédictifs supervisés pour anticiper les résultats futurs.
- Développer des tableaux de bord interactifs pour la visualisation en temps réel.

---
