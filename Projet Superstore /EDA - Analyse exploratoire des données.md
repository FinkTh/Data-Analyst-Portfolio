EDA -  ANALYSE EXPLORATION DES DONNEES 

Distribution des ventes et du profit 
 
   ![Distrib Sales](https://github.com/user-attachments/assets/2ad01135-b02c-45bb-83b7-8bad555aaa10)


   **Interprétation des résultat**


   **Distribution des Ventes (Sales)**

   - **Forme de la distribution** : La distribution des ventes est fortement asymétrique à droite (right-skewed). Cela signifie que la majorité des transactions ont des montants de vente relativement faibles, mais qu'il existe quelques transactions avec des montants de vente très élevés.

   - **Pic à gauche** : Le pic à gauche indique qu'il y a un grand nombre de transactions avec des montants de vente proches de zéro.

   - **Long Tail** : La queue longue à droite montre qu'il y a quelques transactions avec des montants de vente très élevés, mais elles sont rares.

---

   **Distribution des Bénéfices (Profit)**

   - **Forme de la distribution** : La distribution des bénéfices est également asymétrique, mais elle semble plus centrée autour de zéro avec une queue s'étendant vers la droite.

   - **Pic autour de zéro** : Le pic autour de zéro indique que de nombreuses transactions ont des bénéfices proches de zéro.

   - **Valeurs négatives** : Il y a des valeurs négatives de bénéfices, ce qui signifie que certaines transactions ont entraîné des pertes.

   - **Longue Tail** : La queue longue à droite montre qu'il y a quelques transactions avec des bénéfices très élevés, mais elles sont rares.

---

   **Interprétation Globale**

   - **Asymétrie** : Les deux distributions sont asymétriques, ce qui est typique dans de nombreux ensembles de données financières où quelques transactions peuvent avoir des valeurs extrêmement élevées.

   - **Concentration autour de zéro** : La concentration des valeurs autour de zéro pour les bénéfices suggère que de nombreuses transactions ont des marges bénéficiaires faibles ou nulles.

   - **Valeurs aberrantes** : Les valeurs aberrantes (outliers) dans les deux distributions peuvent indiquer des transactions exceptionnelles ou des erreurs de données potentielles.

   **Test de normalité (Shapiro-Wilk et Kolmogorov-Smirnov)**

   👉 Objectif : Nous savons que la distribution ne suit pas une loi normale. La vérification est pour renforcer notre interprétation visuelle et ainsi pouvoir choisir le modèle de prédiction.

   Les résultats des tests de normalité indiquent clairement que la distribution du profit n’est pas normale :

   📌 **Shapiro-Wilk** → p-value ≈ 1.7e-107 (<< 0.05) → Rejet de l’hypothèse de normalité
 
   📌 **Kolmogorov-Smirnov** → p-value ≈ 1e-323 (<< 0.05) → Rejet encore plus fort de la normalité

   💡 Interprétation : 

   🔹 Les profits ont des valeurs extrêmes (outliers) et une asymétrie.

🔹 Une régression linéaire classique pourrait être biaisée si les erreurs ne suivent pas une distribution normale.

🔹 On peut envisager une transformation des données (log) ou un modèle plus robuste (XGBoost, Random Forest).


---

Top 10 des produits chez SuperStore
    
   ![Capture d’écran 2025-03-10 à 15 52 16](https://github.com/user-attachments/assets/cd8d6489-5b33-40b8-b95d-07ccebd003aa)
 
   ![Capture d’écran 2025-03-10 à 15 52 29](https://github.com/user-attachments/assets/d67b433e-6765-4803-85eb-1a0768f43ce9)
 

   Le graphique des meilleures ventes présente les 10 produits ayant généré le plus de chiffre d'affaires. On observe que le **Canon imageCLASS 2200 Advanced Copier** est en tête, avec un volume de ventes nettement supérieur aux autres produits. Cette tendance indique une forte demande ou une performance exceptionnelle pour des produits clé. Les résultats suggèrent qu'il pourrait être bénéfique d'investir davantage dans ces produits ou de comprendre les facteurs de leur succès afin de les appliquer à d'autres segments.

---

Flop 10 des produits chez SuperStore
     
   ![Capture d’écran 2025-03-10 à 15 52 44](https://github.com/user-attachments/assets/1ea353cc-7b5e-4624-982a-dbdd1170c13b)

   ![Capture d’écran 2025-03-10 à 15 52 58](https://github.com/user-attachments/assets/086026ec-6923-43a9-876e-f5f3be26a7ff)


  Le deuxième graphique présente les 10 produits les moins vendus avec une vue détaillée des bénéfices. On constate que chacun de ces produits affiche des pertes en termes de profit. Ceci pourrait résulter de prix de vente trop bas, de coûts élevés, ou de réductions importantes. Il est essentiel d'examiner ces produits de près pour identifier les raisons exactes de ces pertes et déterminer si des ajustements, comme la révision des prix, la modification des stratégies de marketing, ou même le retrait du produit, seraient bénéfiques.
  
---

Comparatif des catégories les plus performantes
       
   ![Capture d’écran 2025-03-10 à 16 06 37](https://github.com/user-attachments/assets/90f37d60-0d25-4f42-92bb-3e1e550b8b00)

   ![Capture d’écran 2025-03-10 à 16 06 57](https://github.com/user-attachments/assets/b8000319-e377-4528-9f9a-373f87016731)
       
      
La marge moyenne par catégorie:
 
   📌Furniture → 3,88%

   📌 Office Supplies → 13,8%

   📌 Technology → 15,61%


   | **Category** | **Profit** |
   | --- | --- |
   | Furniture | 8.699327 |
   | Office Supplies | 20.327050 |
   | Technology | 78.752002 |

   Les résultats montrent clairement que les profits varient énormément selon les catégories de produits :

   📌 Furniture → 8.7 📉 (bas)

   📌 Office Supplies → 20.3 🔄 (moyen)

   📌 Technology → 78.75 🚀 (haut)

   ![Capture d’écran 2025-03-10 à 16 07 25](https://github.com/user-attachments/assets/31abca00-8611-4296-b90b-805530e36822)
     

   **Interprétation**

   - Furniture → Très peu de variance et quelques valeurs négatives → Secteur sensible aux remises 📉

   - Office Supplies → Variabilité un peu plus grande mais profits généralement bas → Stabilité moyenne 🔄

   - Technology → Forte dispersion et des valeurs extrêmes élevées → Secteur très rentable 🚀

   **Conclusion**

   - Les meubles (Furniture) sont les moins rentables, donc les remises doivent être bien contrôlées pour éviter les pertes.

   - Les fournitures de bureau (Office Supplies) sont moyennement rentables, donc un ajustement des remises peut être optimisé.

   - La technologie (Technology) est largement plus rentable, donc elle peut supporter un peu plus de discount sans trop impacter le profit.

---

**Ventilation des ventes et des volumes par sous-catégories**

   ![Capture d’écran 2025-03-10 à 16 13 35](https://github.com/user-attachments/assets/9eaa8ace-4186-47b2-8de4-18a7897b7d0f)


**Top 5 des ventes et des bénéfices dans les sous-catégories**

   ![Capture d’écran 2025-03-10 à 16 14 11](https://github.com/user-attachments/assets/3078ab56-1c5c-4fdd-a01e-c09df5bf6a11)


**Distribution des Remises par Sous-Catégorie de Produits**

Notre boxplot permet de visualiser la distribution des remises pour chaque sous-catégorie de produits et d’identifier les valeurs aberrantes et pouvoir comparer efficacement les sous-catégories.


   ![Capture d’écran 2025-03-10 à 16 15 19](https://github.com/user-attachments/assets/239c6d1e-6d3d-4e50-b0ff-93642ad9c997)


**Observations** **Variations entre Catégories** :

   - **Furniture** : La catégorie Furniture a la moyenne de discount la plus élevée (0.1739), ce qui pourrait indiquer 
     une stratégie de promotion plus agressive pour ces produits.

   - **Office Supplies** : Cette catégorie a une moyenne de discount plus faible (0.1573), mais une variabilité plus 
     élevée (std = 0.2295), ce qui suggère une plus grande diversité dans les réductions offertes.

   - **Technology** : La catégorie Technology a la moyenne de discount la plus faible (0.1323), indiquant peut-être une 
     stratégie de prix plus conservatrice. Variations entre Sous-Catégories :

   - **Binders** : La sous-catégorie Binders a une moyenne de discount très élevée (0.3723), ce qui pourrait être dû à 
     des promotions spécifiques ou à une stratégie de liquidation.

   - **Machines** : La sous-catégorie Machines a également une moyenne de discount élevée (0.3061), ce qui pourrait 
     indiquer des promotions importantes sur ces produits.

   - **Accessories, Art, Envelopes, etc.** : Ces sous-catégories ont des moyennes de discount plus faibles, ce qui 
     pourrait refléter des stratégies de prix différentes.

---

**Analyse de la ventilation des bénéfices et des pertes**

   ![Capture d’écran 2025-03-10 à 16 19 42](https://github.com/user-attachments/assets/58c34f6f-b5ed-4ee4-961e-9e5189dd8360)

   - On remarque qu'il y a des bénéfices négatifs dans un ensemble de données. On va investiguer pour en connaitre les raisons.

   ![Capture d’écran 2025-03-10 à 16 20 21](https://github.com/user-attachments/assets/39fe4eef-c846-4d0b-8510-8dca834d8bbe)

   **Quelques chiffres :** 

   | **Profit Sign** | **Profit** | **Percentage** |
   | --- | --- | --- |
   | **Negative** | -156 131€ | 26.08% |
   | **Positive** | 442 528€ | 73.92% |

 Intuitivement je me dirige vers le problème de "Mode d'expédition".

Cependant il est utile de vérifier les différentes possibilités pour avoir une vision à 360°C

   **Explications potentielles pour un bénéfice négatif** :

   - **Coûts d'expédition** : Si le coût d'expédition dépasse le revenu généré par la vente, cela peut entraîner un 
     bénéfice négatif. Différents modes d'expédition peuvent avoir des coûts variés, certains étant plus élevés que 
     d'autres.

   - **Réductions ou promotions** : Si des réductions ou promotions importantes sont appliquées à certaines commandes, 
     le revenu des ventes peut ne pas couvrir les coûts, entraînant un bénéfice négatif.

   - **Retours ou marchandises endommagées** : Si des marchandises sont retournées ou endommagées pendant l'expédition, 
     les coûts associés à ces retours ou dommages peuvent dépasser le revenu, entraînant une perte.

   - **Inefficacités opérationnelles** : Les inefficacités dans la chaîne d'approvisionnement ou les processus 
     opérationnels peuvent entraîner des coûts plus élevés, qui peuvent ne pas être compensés par le revenu des ventes.

   - **Stratégie de tarification** : Dans certains cas, une stratégie de tarification peut intentionnellement fixer des 
     prix bas pour capturer des parts de marché ou liquider des stocks, même si cela entraîne une perte à court terme.

Dans le cadre de étude actuelle, nous ne disposons pas de données nécessaires pour évaluer les **retours ou marchandises endommagées**, les **inefficacités opérationnelles** ainsi que la **stratégie de tarification**. Les informations disponibles ne sont pas adaptées à ces analyses.

Pour approfondir notre enquête, nous allons dans un premier temps analyser les données afin de déterminer s'il existe **une corrélation univariée entre le "Mode d'expédition" et le bénéfice négatif**.

Dans un second temps nous analyserons l'impact des **réductions et promotions** sur ces mêmes bénéfices négatifs.

   ![Capture d’écran 2025-03-10 à 16 22 32](https://github.com/user-attachments/assets/c9323249-1784-489c-bc70-6003e96988eb)

  
   
