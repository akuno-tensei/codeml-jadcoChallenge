# JADCO CodeML 2026 — Collection Équinoxe

## Résultat

- Estimation principale : **3,3 %** de hausse contractuelle 2026 pour les renouvellements à unité constante.
- Lecture de trésorerie centrale : **environ 2,4 %** de croissance du loyer effectif si 25 % de la dernière détérioration des concessions persiste.
- Plage contractuelle de planification : **2,3 % à 4,3 %**.
- Erreur absolue moyenne du backtest 2023–2025 : **environ 0,7 point**, contre environ 2,3 points pour la prolongation de la dernière année.

## Fichiers

- `solution_jadco_2026.ipynb` : livrable principal, entièrement exécuté.
- `presentation_jury_jadco_2026.pptx` : présentation éditable pour le jury.
- `pitch_jury.md` : trame orale et réponses aux questions probables.

Les quatre CSV CRM ne sont pas inclus dans ce dossier.

## Exécution

Python 3.12 recommandé.

```powershell
python -m pip install pandas numpy matplotlib seaborn jupyter
$env:JADCO_DATA_DIR = "C:\chemin\vers\jadco-participants"
jupyter notebook solution_jadco_2026.ipynb
```

Le notebook cherche aussi les CSV dans le dossier courant, `jadco-participants/` et `../jadco-participants/`.

## Définition retenue

La métrique principale est la moyenne pondérée des médianes provinciales de la croissance annualisée du loyer contractuel entre deux baux consécutifs de la même unité (`sPropCode + sUnitCode`), limitée aux renouvellements. Les poids viennent des baux connus qui arrivent à échéance en 2026.

Cette définition évite l'effet de composition et correspond à la décision de fixation du prochain bail. Le loyer effectif est présenté séparément pour mesurer l'impact des concessions.

## Hypothèses importantes

- Les cinq immeubles du Québec utilisent le paramètre TAL 2026 de 3,1 % comme ancre.
- The Met est traité comme immeuble récent probablement exempté du plafond ontarien; JADCO doit confirmer la première date d'occupation.
- L'ancre de The Met combine son historique et la prévision SCHL d'Ottawa.
- Le scénario effectif central prolonge 25 % de la détérioration 2024–2025 du facteur loyer effectif/contractuel.
- Aucune mesure d'occupation, d'inoccupation, d'absorption ou de rôle de loyers total n'est produite à partir de l'extrait.

## Versions validées

- Python 3.12
- pandas 3.0.1
- NumPy 2.3.5
- matplotlib 3.11.2
- seaborn 0.13.2

## Sources publiques

- TAL, pourcentages 2026 : https://www.tal.gouv.qc.ca/fr/reconduction-du-bail-et-fixation-de-loyer/pourcentages-applicables-aux-criteres-de-fixation-de-loyer
- Ontario, lignes directrices et exemptions : https://www.ontario.ca/page/residential-rent-increases
- SCHL, Rapport sur le marché locatif 2025 : https://www.cmhc-schl.gc.ca/professionnels/marche-du-logement-donnees-et-recherche/marches-de-lhabitation/rapports-sur-le-marche-locatif
- SCHL, Perspectives du marché 2025–2027 : https://www.cmhc-schl.gc.ca/observer/2025/summer-update-2025-housing-market-outlook
- Statistique Canada, IPC des loyers : https://www150.statcan.gc.ca/n1/daily-quotidien/251021/cg-a005-fra.htm

## IA

OpenAI Codex a aidé à structurer le code, vérifier les calculs, rédiger la documentation et préparer les livrables. Les calculs restent reproductibles et les sources sont citées dans le notebook.
