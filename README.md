# Détection de Fraude sur les Transactions de Cartes de Crédit

## Description du Projet
Ce notebook analyse un dataset simulé de transactions de cartes de crédit contenant des transactions légitimes et frauduleuses de janvier 2019 à décembre 2020. Le dataset couvre les cartes de crédit de 1000 clients effectuant des transactions avec 800 marchands.

## Objectifs
- Explorer et analyser les patterns de fraude
- Développer des modèles de machine learning pour détecter la fraude
- Évaluer et comparer les performances des différents modèles
- Identifier les facteurs clés dans la détection de fraude

## Dataset
- **Source**: Kaggle - Credit Card Transactions Fraud Detection Dataset
- **Période**: 1er janvier 2019 - 31 décembre 2020
- **Clients**: 1000 clients
- **Marchands**: 800 marchands
- **Générateur**: Sparkov Data Generation (Brandon Harris)

## Méthodologie

### Exploration des Données (EDA)
- Analyse de la distribution des transactions
- Identification des patterns temporels et géographiques
- Étude des corrélations entre variables

### 2. Feature Engineering
- **Caractéristiques temporelles**: heure, jour de la semaine, weekend/nuit
- **Caractéristiques géographiques**: distance entre domicile et transaction
- **Caractéristiques comportementales**: statistiques par client, moyennes mobiles
- **Encodage**: variables catégorielles (genre, état, profession, catégorie)

### 3. Modélisation
- **Régression Logistique**: Modèle de base rapide et interprétable
- **Random Forest**: Modèle ensemble robuste aux non-linéarités
- **XGBoost**: Modèle de gradient boosting haute performance

### 4. Évaluation et Optimisation
- Métriques: Accuracy, Precision, Recall, F1-Score, ROC-AUC
- Optimisation du seuil de classification
- Analyse des coûts (faux positifs vs faux négatifs)

## Résultats

### Performance des Modèles
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Model</th>
      <th>Accuracy</th>
      <th>Precision</th>
      <th>Recall</th>
      <th>F1-Score</th>
      <th>ROC-AUC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <th>Logistic Regression</th>
      <td>0.9485</td>
      <td>0.0845</td>
      <td>0.9036</td>
      <td>0.1545</td>
      <td>0.9721</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Random Forest</td>
      <td>0.9829</td>
      <td>0.2277</td>
      <td>0.9580</td>
      <td>0.3680</td>
      <td>0.9956</td>
    </tr>
    <tr>
      <th>2</th>
      <td>XGBoost</td>
      <td>0.9933</td>
      <td>0.4378</td>
      <td>0.9782</td>
      <td>0.6049</td>
      <td>0.9989</td>
    </tr>
  </tbody>
</table>
</div>

*Note: Les résultats exacts peuvent varier selon l'exécution*

## Conclusions

### Résultats Principaux

1. **Performance des Modèles**: Les trois modèles testés (Régression Logistique, Random Forest, XGBoost) ont montré de bonnes performances, avec des scores ROC-AUC supérieurs à 0.9.

2. **Détection de Fraude**: Le modèle optimal peut détecter environ 85-95% des fraudes tout en maintenant un taux de faux positifs acceptable.

3. **Facteurs Clés**: Les facteurs les plus importants pour la détection incluent:
   - Le montant de la transaction
   - La distance par rapport au domicile
   - L'heure de la transaction
   - Les patterns comportementaux du client

---
*Ce projet est à des fins éducatives et de démonstration. Pour une utilisation en production, des considérations supplémentaires de sécurité et de conformité sont nécessaires.*