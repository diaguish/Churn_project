# Customer Churn Prediction

## 📌 Objectif
LL’objectif de ce projet était de prédire le churn client à partir de données télécom.

Une première régression logistique a montré une bonne accuracy mais un recall très faible, ce qui signifiait que la majorité des clients churners n’étaient pas détectés.

Afin de répondre à la problématique métier, le modèle a été réentraîné en utilisant class_weight="balanced" pour accorder plus d’importance à la classe minoritaire (clients churners).

Cette approche a permis d’augmenter fortement le recall (≈ 80 %), réduisant ainsi le nombre de churners ratés, au prix d’une baisse de la precision (≈ 39 %).

Ce compromis est pertinent dans un contexte churn, où rater un client est plus coûteux que générer une fausse alerte.

Les résultats montrent qu’un modèle simple, bien interprété et aligné avec les objectifs métier, peut déjà apporter une réelle valeur.


## 📊 Dataset
Le dataset utilisé contient des informations sur des clients télécom :
- ancienneté du client
- usage des services
- nombre d’appels au service client
- facturation
- variable cible : `Churn` (0 = reste, 1 = quitte)

## 🧠 Méthodologie
1. Analyse exploratoire des données (EDA)
2. Identification de la variable cible et des variables explicatives
3. Séparation des données en train / test
4. Entraînement d’un modèle de régression logistique
5. Évaluation avec accuracy, confusion matrix, recall et precision
6. Amélioration du modèle avec `class_weight="balanced"`

## 📈 Résultats
- Accuracy : ~78 %
- Recall : ~80 %
- Precision : ~39 %

Le modèle est volontairement optimisé pour maximiser le recall afin de limiter le nombre de clients churners non détectés, ce qui entraîne une augmentation des fausses alertes.

## 🎯 Conclusion métier
Dans un contexte churn, il est préférable de détecter un maximum de clients à risque, même au prix de fausses alertes, car rater un client entraîne une perte directe.  
Le modèle proposé répond à cet objectif et constitue une base solide pour une mise en production ou des améliorations futures.

## 🔧 Améliorations possibles
- Ajustement du seuil de décision
- Test de modèles plus complexes (Random Forest)
- Intégration de nouvelles variables
- Optimisation du compromis recall / precision

## 🛠️ Technologies
- Python
- Pandas
- Scikit-learn
- Matplotlib / Seaborn

