# videos-games

Ce projet vise à prédire l'âge recommandé pour les jeux vidéo en fonction de diverses caractéristiques extraites de leur description, telles que les genres, le prix, et les descripteurs de contenu.
Modèle Utilisé
Le modèle choisi pour ce problème est la régression linéaire, une méthode couramment utilisée pour établir une relation linéaire entre les variables prédictives et la cible.

# videos-games
# Variables Prédictives

Les variables utilisées pour prédire l'âge rating sont :
•	sport
•	education
•	free_play
•	animation_modeling
•	action
•	simulation
•	racing
•	video_production
•	violence
•	sex
•	drugs
•	bad
•	blood
Ces variables sont binaires et indiquent la présence ou l'absence de certaines caractéristiques dans la description des jeux.

# videos-games
# Entraînement du Modèle

Le modèle a été entraîné sur un ensemble de données divisé aléatoirement en un ensemble d'entraînement (80%) et un ensemble de test (20%). Les performances du modèle ont été évaluées sur l'ensemble de test.

# videos-games
# Performance

•	Mean Squared Error (MSE) : Le MSE mesure l'erreur quadratique moyenne entre les prédictions du modèle et les valeurs réelles de l'âge rating. Pour ce modèle, le MSE obtenu est de 0.0123.
•	R-squared (R²) : Le R² est une mesure de l'adéquation du modèle aux données. Pour ce modèle, un R² de 0.78 indique que le modèle explique 78% de la variance de la variable cible.

# videos-games
# Interprétation des Coefficients

Les coefficients du modèle indiquent la contribution de chaque variable prédictive à la prédiction de l'âge rating. Par exemple, un coefficient positif pour une caractéristique comme "violence" pourrait indiquer une tendance à obtenir un âge rating plus élevé.
Coefficients du Modèle :
Coefficients: [ 0.015 -0.024 0.036 -0.015 0.025 -0.034 0.021 0.019 0.123 0.011 -0.027 0.009 0.017] Intercept: 0.55

# videos-games
# Utilisation du Modèle

Le modèle entraîné est sauvegardé dans le fichier video_game_lr_model.pkl à des fins de déploiement ou d'utilisation ultérieure. Pour charger le modèle et faire des prédictions, vous pouvez utiliser le module pickle de Python.

# videos-games
# Utilisation du Modèle

Le modèle entraîné est sauvegardé dans le fichier video_game_lr_model.pkl à des fins de déploiement ou d'utilisation ultérieure. Pour charger le modèle et faire des prédictions, vous pouvez utiliser le module pickle de Python.
python
Copier le code
import pickle

with open('video_game_lr_model.pkl', 'rb') as file:
    model = pickle.load(file)

# Exemple de prédiction
predictions = model.predict(X_test)
