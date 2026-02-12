---
titre: "Détection de Fraude – Carte de Crédit"
---
auteur: "Aissa Cheroufa"
localisation: "Canada"
type_projet: "Machine Learning – Classification supervisée"

jeu_de_donnees:
  source: "Kaggle – Credit Card Fraud Detection (ULB)"
  Taille du dataset: 284807
  desequilibre:
    transactions_legitimes: "99.83%"
    transactions_frauduleuses: "0.17%"
  variables:
    - Time
    - Amount
    - V1 à V28 (variables issues d’une PCA)
    - Class (0 = légitime, 1 = fraude)

objectif: >
  Développer un pipeline complet d’intelligence artificielle
  permettant de détecter les transactions frauduleuses
  dans un dataset bancaire fortement déséquilibré.

contexte_affaires:
  - Réduction des pertes financières
  - Protection des clients
  - Détection rapide des transactions suspectes
  - Amélioration des systèmes de sécurité bancaire

defis:
  - Déséquilibre extrême des classes
  - Variables anonymisées (PCA) peu interprétables
  - Distribution très asymétrique de la variable Amount
  - Métriques classiques potentiellement trompeuses

ingenierie_des_variables:
  transformations:
    - Transformation logarithmique de Amount
    - Conversion de Time en heures
  nouvelles_variables:
    - Amount_per_hour
    - Is_night

gestion_du_desequilibre:
  - Baseline (pondération des classes)
  - SMOTE
  - Random Under-Sampling
  - SMOTE + Tomek Links

modeles_testes:
  - Autoencodeur (Deep Learning)
  - Régression Logistique pondérée
  - XGBoost

metriques_evaluation:
  metrique_principale: "PR AUC"
  metrique_secondaire: "ROC AUC"
  justification: >
    La métrique PR AUC est plus pertinente que le ROC AUC
    dans un contexte de classes fortement déséquilibrées.

resultats:
  meilleur_modele: "XGBoost + SMOTE + Tomek Links"
  observations:
    - SMOTE améliore significativement la détection des fraudes
    - Random Under-Sampling entraîne une perte importante d’information
    - Le ROC AUC peut masquer les performances réelles
    - Le PR AUC reflète mieux la capacité à détecter la fraude

conclusion: >
  Ce projet démontre l’importance de comprendre le contexte d’affaires,
  de choisir des métriques adaptées et d’appliquer des techniques
  spécifiques pour traiter les données déséquilibrées.

technologies:
  - Python
  - Pandas
  - NumPy
  - Scikit-learn
  - XGBoost
  - Imbalanced-learn
  - Matplotlib
  - Seaborn
---



