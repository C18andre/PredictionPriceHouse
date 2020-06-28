## Modèle

Mise en Place d'un modèle prédictif de la valeur foncière lors d'une vente d'un appartement ou d'une maison

## Fichiers 

Les fichiers trop volumineux sont dans le .gitignore

## Librairies

Installer les librairies via `pip install -r requirements.txt`

## Architecture du Projet

- Projet (Preprocessing,Modeles,Config,Results,Data,TrainingData)
- requirements.txt
- Main.py
- Presentation.ipynb

## Documentation

En premier lieu, je me suis documenté sur ce qui impactait la valeur d'un logement

Les critères principaux sont :
 - La situation du bien
 - Son état
 - Terrain extéreur
 - Étage (Pour les appartements)
 - Différents lots

Références :

 - [1] : https://immobilier.lefigaro.fr/annonces/edito/acheter/les-prix-de-l-immobilier/immobilier-comment-estimer-plus-facilement-votre-bien-grace-au-big-data

 - [2] : https://www.economie.gouv.fr/cedef/estimer-prix-immobilier

## Filtrage des données

 - Suppression des colonnes vides 
 - On garde uniquement les ventes sur des Maisons et Appartements
 - Afin de s'assurer de la qualité des données, je choisis de supprimer les ventes de moins de 10 000€
 - Choix d'une ville ou d'un département, car les prix son très dépendant de la situation d'un bien

## Choix des Paramètres

Après avoir choisit une ville,
Les colonnes des données que j'ai considéré utile à la prédiction :
( Celles sui se rapprochent le plus des critères principaux)

- Valeur Foncière : Target donc obligatoire
- Nombre de lots dans une maison 
- Les surfaces et type de lots
- Type local
- Surface réelle
- Nombre de pièces principales
- Surface terrain

## Normalisation des données

Afin que le modèle puisse apprendre au vu de la disparité des valeurs, je choisis de normaliser les données grâce à scikit-learn (MinMaxScaler,StandardScaler)

## Différents modèles

 - LSTM
 - XGBoost
 - RandomForestRegressor (Pratique pour l'explicabilité d'un modèle)
