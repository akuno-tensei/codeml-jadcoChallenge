# Trame jury : 5 minutes

## 0:00 à 0:35 · Réponse

« Notre recommandation est une hausse contractuelle de 3,3 % pour les renouvellements 2026, mesurée à unité constante. Pour le budget de trésorerie, nous retenons environ 2,4 % de croissance effective si une partie de l'intensification des concessions persiste. »

## 0:35 à 1:20 · Pourquoi la moyenne naïve échoue

La médiane de tous les baux bondit quand Le Carlyle, The Met et Westpark entrent dans l'échantillon. Elle mélange prix et composition. Nous apparions donc chaque unité à son bail précédent avec `sPropCode + sUnitCode`.

## 1:20 à 2:05 · Deux prix, deux décisions

Le contractuel sert à fixer le prochain bail. L'effectif sert à budgéter l'encaissement. En 2025, la croissance contractuelle à unité constante approche 7 %, mais l'effective seulement 3,6 %. Les concessions expliquent l'écart.

## 2:05 à 3:10 · Modèle

Au Québec, l'ancre est le paramètre TAL 2026 de 3,1 %. En Ontario, The Met semble postérieur à novembre 2018 et probablement exempté du plafond. Son ancre combine son historique et la prévision SCHL d'Ottawa. Les poids viennent des baux qui arrivent à échéance en 2026.

## 3:10 à 3:55 · Validation

Le backtest strict sur 2023, 2024 et 2025 produit environ 0,7 point d'erreur absolue moyenne. Prolonger seulement la dernière année produit environ 2,3 points. Le modèle gagne surtout parce qu'il respecte le régime réglementaire au lieu de poursuivre aveuglément la tendance.

## 3:55 à 4:35 · Décision

Budget contractuel : 3,3 %. Plage de planification : 2,3 % à 4,3 %. Budget de trésorerie central : environ 2,4 %. Mise à jour mensuelle dès que les concessions 2026 sont connues.

## 4:35 à 5:00 · Risque à confirmer

Le point juridique à vérifier est la première date d'occupation de The Met. Si l'immeuble n'est pas exempté, remplacer son ancre par la ligne directrice ontarienne de 2,1 % fait légèrement baisser la cible portefeuille.

## Questions probables

**Pourquoi ne pas prévoir toutes les relocations?**  
La demande exige une définition défendable. Le renouvellement contractuel est la décision la plus contrôlable et la mieux reliée aux règles provinciales. Les relocations et le loyer effectif restent visibles comme analyses secondaires.

**Pourquoi pas XGBoost?**  
Il n'y a que neuf années et les régimes ont changé. Un modèle complexe apprendrait surtout le calendrier et le mix. L'approche retenue est auditable, backtestée et directement reliée aux règles.

**Le TAL impose-t-il exactement 3,1 %?**  
Non. C'est un pourcentage de base entrant dans le calcul. Le résultat d'un logement dépend de ses dépenses, taxes et travaux. Nous l'utilisons comme ancre de portefeuille, pas comme vérité individuelle.

**Pourquoi 25 % de persistance des concessions?**  
C'est un scénario central explicite. Comme environ 85 % des baux ont déjà une concession en 2025, prolonger 100 % de la détérioration serait agressif. Le notebook montre aussi 0 % et 50 %.

**Que feriez-vous avec plus de données?**  
Ajouter le rôle de loyers complet, les dépenses par immeuble, la première date d'occupation, les refus/acceptations de renouvellement et les concessions offertes en 2026. Ensuite, recalibrer par immeuble et type d'unité.
