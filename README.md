# credit-analysis

## **Prédiction du risque de défaut de crédit**

### **Projet de machine learning pour les institutions financières**

Ce projet a pour but de développer et d'évaluer des modèles de machine learning pour prédire le risque de défaut de paiement des emprunteurs. L'objectif est d'aider les institutions financières à prendre des décisions plus éclairées en matière d'octroi de crédit, en réduisant les pertes et en optimisant la gestion des risques. Ce projet fait partie de notre formation en **Data Science** et suit une démarche rigoureuse, de la compréhension du problème à la modélisation et aux recommandations finales.

---

### **Compréhension du problème métier et des données**

#### **Public cible**
Ce projet s'adresse principalement aux **responsables de risques financiers**, aux **analystes de crédit** et aux **cadres dirigeants** des institutions financières. L'objectif est de leur fournir une solution pour moderniser leur processus d'évaluation du risque de crédit, en complétant leurs méthodes traditionnelles par une approche analytique et prédictive.

#### **Choix du jeu de données**
Pour ce projet, nous avons utilisé le jeu de données **"Give Me Some Credit"** disponible sur Kaggle. Ce jeu de données a été choisi car il est représentatif d'un problème réel et complexe dans le domaine financier. Il permet de travailler sur des aspects essentiels du machine learning, tels que l'équilibrage des classes et la gestion des valeurs manquantes, tout en fournissant des variables pertinentes pour la modélisation.

#### **Description des données**
Le jeu de données se compose de 150 000 observations et de 11 variables décrivant le profil financier et démographique des emprunteurs. Les variables clés incluent le taux d'endettement, le revenu mensuel et l'historique des retards de paiement (30-59 jours, 60-89 jours et 90 jours ou plus). Ces variables sont essentielles car elles capturent le comportement de remboursement passé, un indicateur fort du risque futur.

#### **Variable cible**
La variable cible, `SeriousDlqin2yrs`, est binaire et indique si un emprunteur a eu des difficultés financières graves au cours des deux dernières années.
* **Valeur 1 :** L'emprunteur a connu des difficultés financières sérieuses, ce qui correspond à un défaut de paiement ou un retard important.
* **Valeur 0 :** L'emprunteur n'a pas connu de tels événements.

---

### **Modélisation**

Après une phase de nettoyage et de prétraitement des données (incluant la gestion des valeurs manquantes et l'encodage), nous avons développé et entraîné trois modèles de machine learning :

1.  **Régression logistique** : Un modèle de référence simple et très interprétable, utilisé pour établir une première ligne de base. Il a aidé à identifier les variables les plus influentes, comme les retards de paiement et le taux d'endettement, et leur impact sur le risque.
2.  **Arbre de décision** : Ce modèle permet de capturer des relations non-linéaires et est utile pour visualiser les chemins menant au défaut de paiement.
3.  **Forêt aléatoire (Random Forest)** : Une méthode d'ensemble qui agrège les prédictions de multiples arbres de décision. Elle est plus robuste que les modèles individuels, car elle réduit le surapprentissage et améliore la précision globale.

---

### **Évaluation des modèles**

Pour évaluer la performance de chaque modèle, nous avons utilisé plusieurs métriques, en nous concentrant particulièrement sur la **précision**, le **rappel** et la **courbe ROC (Receiver Operating Characteristic)**.
* **Précision** : Indique la proportion de prédictions positives (risque de défaut) qui sont réellement correctes.
* **Rappel** : Mesure la capacité du modèle à identifier tous les clients qui vont réellement faire défaut. Un rappel élevé est crucial dans ce contexte pour minimiser les pertes financières.
* **AUC-ROC** : L'aire sous la courbe ROC est une mesure globale de la capacité du modèle à distinguer les clients à risque des clients solvables. Un score proche de 1 indique une performance excellente.

#### **Résultats comparatifs**
| Modèle | Précision | Rappel | AUC-ROC |
|---|---|---|---|
| Régression Logistique | 0,201 | 0,618 | 0,783 |
| Arbre de décision | 0,182 | 0,778 | 0,829 |
| **Forêt aléatoire** | **0,212** | **0,743** | **0,846** |

**Analyse des résultats :** Le modèle de **Forêt aléatoire** s'est avéré être le plus performant. Il a obtenu le meilleur score AUC-ROC et a démontré le meilleur compromis entre un rappel élevé (capacité à détecter une grande partie des clients à risque) et une bonne précision.

---

### **Conclusion**

Le projet a démontré l'efficacité du machine learning, et plus particulièrement des modèles d'ensemble comme la Forêt aléatoire, pour la prédiction du risque de crédit. Le modèle final est un outil précieux pour les institutions financières :
* Il peut être intégré dans un système d'aide à la décision pour signaler les demandes de prêt les plus risquées.
* Il permet une meilleure allocation des ressources en ciblant les efforts de gestion de risque sur les clients les plus susceptibles de faire défaut.
* Il offre un niveau de performance supérieur aux modèles de régression logistique et aux arbres de décision simples, ce qui en fait le choix recommandé pour une mise en production.
