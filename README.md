# Bilanconso

**Application Shiny Dashboard** interactive pour analyser la **production électrique par filière** (photovoltaïque, éolien, hydraulique, bioénergie, cogénération, autres) et la **consommation par secteur d'activité** en France aux mailles région/département/commune.

**IMPORTANT** : Fichiers CSV Enedis **très volumineux** - **télécharger manuellement** (liens ci-dessous).

## Fonctionnalités
- Comparaison conso/prod en barres TWh juxtaposées
- Évolution temporelle interactive Plotly
- ValueBox totaux production/consommation
- Tableaux détaillés + export CSV
- Filtres multi-mailles + années multiples
- Moyennes France comme référence

## Packages requis

install.packages(c("shiny", "shinydashboard", "ggplot2", "plotly", "ggnewscale", "dplyr", "tidyr", "stringr"))

## Installation (3 étapes)

### 1/ Télécharger les 6 CSV dans `Bilanconso/`
**PRODUCTION** :
- [Région](https://data.enedis.fr/explore/dataset/production-electrique-par-filiere-a-la-maille-region/export/)
- [Département](https://data.enedis.fr/explore/dataset/production-electrique-par-filiere-a-la-maille-departement/export/)
- [Commune](https://data.enedis.fr/explore/dataset/production-electrique-par-filiere-a-la-maille-commune/export/)

**CONSO** :
- [Région](https://data.enedis.fr/explore/dataset/consommation-electrique-par-secteur-dactivite-region/export/)
- [Département](https://data.enedis.fr/explore/dataset/consommation-electrique-par-secteur-dactivite-departement/export/)
- [Commune](https://data.enedis.fr/explore/dataset/consommation-electrique-par-secteur-dactivite-commune/export/)

### 2/ Nettoyer les données

source("Bilanconso/cleandata.R")

### 3/ Lancer l'app

shiny::runApp("Bilanconso/app.R")

## Structure
Bilanconso/
├── app.R # Dashboard Shiny
├── cleandata.R # Nettoyage données
└── README.md


## 🔧 `cleandata.R` fait :
- Nettoie noms (accents→e, points→_)
- NA→0 + pivot long (6 filières)
- Moyennes France/région/département
- Sauvegarde 6 fichiers .rds

## Auteurs
**Rémy**
*Données open data Enedis*
