
DISTRIBUTION DES VENTES ET DU PROFIT 
 
   ![Distrib Sales](https://github.com/user-attachments/assets/2ad01135-b02c-45bb-83b7-8bad555aaa10)


**Interprétation des résultat**


**Distribution des Ventes (Sales)**

**Forme de la distribution** : La distribution des ventes est fortement asymétrique à droite (right-skewed). Cela signifie que la majorité des transactions ont des montants de vente relativement faibles, mais qu'il existe quelques transactions avec des montants de vente très élevés.

**Pic à gauche** : Le pic à gauche indique qu'il y a un grand nombre de transactions avec des montants de vente proches de zéro.

**Long Tail** : La queue longue à droite montre qu'il y a quelques transactions avec des montants de vente très élevés, mais elles sont rares.

---

**Distribution des Bénéfices (Profit)**

**Forme de la distribution** : La distribution des bénéfices est également asymétrique, mais elle semble plus centrée autour de zéro avec une queue s'étendant vers la droite.

**Pic autour de zéro** : Le pic autour de zéro indique que de nombreuses transactions ont des bénéfices proches de zéro.

**Valeurs négatives** : Il y a des valeurs négatives de bénéfices, ce qui signifie que certaines transactions ont entraîné des pertes.

**Longue Tail** : La queue longue à droite montre qu'il y a quelques transactions avec des bénéfices très élevés, mais elles sont rares.

---

**Interprétation Globale**

**Asymétrie** : Les deux distributions sont asymétriques, ce qui est typique dans de nombreux ensembles de données financières où quelques transactions peuvent avoir des valeurs extrêmement élevées.

**Concentration autour de zéro** : La concentration des valeurs autour de zéro pour les bénéfices suggère que de nombreuses transactions ont des marges bénéficiaires faibles ou nulles.

**Valeurs aberrantes** : Les valeurs aberrantes (outliers) dans les deux distributions peuvent indiquer des transactions exceptionnelles ou des erreurs de données potentielles.

**Test de normalité (Shapiro-Wilk et Kolmogorov-Smirnov)**

👉 Objectif : Nous savons que la distribution ne suit pas une loi normale. La vérification est pour renforcer notre interprétation visuelle et ainsi pouvoir choisir le modèle de prédiction.

Les résultats des tests de normalité indiquent clairement que la distribution du profit n’est pas normale :

📌 **Shapiro-Wilk** → p-value ≈ 1.7e-107 (<< 0.05) → Rejet de l’hypothèse de normalité

📌 **Kolmogorov-Smirnov** → p-value ≈ 1e-323 (<< 0.05) → Rejet encore plus fort de la normalité

💡 Interprétation : 

🔹 Les profits ont des valeurs extrêmes (outliers) et une asymétrie.

🔹 Une régression linéaire classique pourrait être biaisée si les erreurs ne suivent pas une distribution normale.

🔹 On peut envisager une transformation des données (log) ou un modèle plus robuste (XGBoost, Random Forest).






--------------------------------------------------------------------------------------------------------------------------------
- Ventilation des ventes et du profit
  - Top 10 des produits chez SuperStore
    
    ![Top 10 des ventes en terme de CA](Picture%20for%20README/Top%2010%20ventes.png)
    ![Top 10 stack des Bénéfices](Picture%20for%20README/Top%2010%20stack%20Benef.png)

  Le graphique des meilleures ventes présente les 10 produits ayant généré le plus de chiffre d'affaires. On observe que le **Canon imageCLASS 2200 Advanced Copier** est en tête, avec un volume de ventes nettement supérieur aux autres produits. Cette tendance indique une forte demande ou une performance exceptionnelle pour des produits clé. Les résultats suggèrent qu'il pourrait être bénéfique d'investir davantage dans ces produits ou de comprendre les facteurs de leur succès afin de les appliquer à d'autres segments.
  
    - Flop 10 des produits chez SuperStore
     
      ![Top Flop vente](Picture%20for%20README/Top%20Flop%20vente.png)
      ![Top flop avec Bénéfice](Picture%20for%20README/Top%20flop%20avec%20Benef.png)

  Le deuxième graphique présente les 10 produits les moins vendus avec une vue détaillée des bénéfices. On constate que chacun de ces produits affiche des pertes en termes de profit. Ceci pourrait résulter de prix de vente trop bas, de coûts élevés, ou de réductions importantes. Il est essentiel d'examiner ces produits de près pour identifier les raisons exactes de ces pertes et déterminer si des ajustements, comme la révision des prix, la modification des stratégies de marketing, ou même le retrait du produit, seraient bénéfiques.

    - Comparatif des catégories les plus performantes
       
        ![Image by cat](Picture%20for%20README/by%20cat.png)
        ![Image by cat](Picture%20for%20README/marge%20by%20cat.png)       
      
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

   ![Image by cat](Picture%20for%20README/rep%20mar.png)       


**Interprétation**

   📌 Furniture → Très peu de variance et quelques valeurs négatives → Secteur sensible aux remises 📉

   📌 Office Supplies → Variabilité un peu plus grande mais profits généralement bas → Stabilité moyenne 🔄

   📌 Technology → Forte dispersion et des valeurs extrêmes élevées → Secteur très rentable 🚀

**Conclusion**

   ✅ Les meubles (Furniture) sont les moins rentables, donc les remises doivent être bien contrôlées pour éviter les pertes.

   ✅ Les fournitures de bureau (Office Supplies) sont moyennement rentables, donc un ajustement des remises peut être optimisé.

   ✅ La technologie (Technology) est largement plus rentable, donc elle peut supporter un peu plus de discount sans trop impacter le profit.


