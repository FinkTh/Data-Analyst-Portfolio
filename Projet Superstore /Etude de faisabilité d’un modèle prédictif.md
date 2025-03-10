L'objectif initial était d'évaluer la faisabilité d'un modèle prédictif permettant d'optimiser les remises de manière data-driven.

**BASELINE MODEL :**

- Les colonnes de notre dataset

![Capture d’écran 2025-03-10 à 18 15 25](https://github.com/user-attachments/assets/19f3a85f-faea-4ffa-a461-4556a88b7e39)

- Code du baseline model avec un logarithme

![Capture d’écran 2025-03-10 à 18 16 45](https://github.com/user-attachments/assets/2712a270-514c-438a-878d-d54b3f5e0ce6)
![Capture d’écran 2025-03-10 à 18 17 12](https://github.com/user-attachments/assets/680ce345-1890-40b1-af1c-7ef3fc7bb413)

Caractéristiques catégorielles finales : ['Ship Mode', 'Segment', 'Region', 'State', 'Category', 'Sub-Category', 'Profit Sign']

Caractéristiques numériques finales : ['Discount', 'Sales', 'Quantity', 'Profit_margin']

Score du modèle sur l'ensemble de test : -0.03

- Code du baseline model avec un RandomForest

![Capture d’écran 2025-03-10 à 18 18 02](https://github.com/user-attachments/assets/1e4fe4c3-0e7b-4645-b3b8-180303df94ea)


### Analyse globale des modèles prédictifs d'optimisation des remises

L’objectif initial était d’évaluer la faisabilité d’un modèle prédictif pour optimiser les remises, en cherchant à maximiser le profit tout en maintenant une approche data-driven. 

Après plusieurs itérations, nous avons testé différentes approches, dont une régression logarithmique et un modèle de Random Forest.

### 🔍 Résultats des modèles testés

- **Régression Logarithmique**
    - Score R² : **0.03**
    - L’obtention d’un score négatif indique que le modèle n’explique pas la variance des données et fait pire qu’un simple prédicteur basé sur la moyenne.
    - Hypothèses expliquant ce résultat :
        - La transformation logarithmique de la variable cible n'est peut-être pas adaptée.
        - La relation entre les variables explicatives et la cible pourrait être trop complexe pour une approche linéaire.
        - Les features sélectionnées pourraient ne pas être suffisamment informatives.
- **Random Forest (sans y_shifted)**
    - Score R² : **0.15**
    - Cette amélioration par rapport au modèle linéaire montre que Random Forest capture mieux certaines relations non linéaires, mais reste insuffisant pour une prédiction fiable.
    - Points d'attention :
        - Les features doivent être affinées pour améliorer la prédiction.
        - Des hyperparamètres plus optimisés pourraient renforcer la robustesse du modèle.
        - La présence potentielle de valeurs aberrantes ou d’un bruit important dans les données peut limiter la performance.
     
### 📊 Interprétation et prochaines étapes

Ces résultats mettent en lumière les défis liés à la modélisation des remises. L’écart significatif entre les modèles suggère que :

1. L’approche linéaire est trop simpliste et ne capte pas la complexité du problème.
2. L’amélioration de la sélection de features et du préprocessing pourrait augmenter la performance.
3. L’exploration d’un modèle bayésien et l’intégration d’ElasticNet sont des pistes prometteuses.

L’objectif final reste d’identifier une approche robuste permettant d’optimiser les remises tout en maximisant le profit, avec un modèle à la fois explicable et actionnable pour la prise de décision.
