## Pipeline de Prédiction des Formes des Nanoparticules

Ce pipeline permet de prédire la forme des nanoparticules à partir de données d'intensité mesurées.

### 1. Objectif du Pipeline
- **Entrée :** Intensités mesurées des nanoparticules.
- **Sortie :** Prédictions des formes des nanoparticules, retournées sous forme de noms de classes.

### 2. Étapes du Pipeline
- **Transformation Logarithmique :** Applique une transformation logarithmique sur les intensités pour les rendre plus adaptées au modèle.
- **Normalisation des Données :** Utilise un scaler pré-entraîné pour normaliser les données.
- **Prédiction avec Modèle :** Le modèle pré-entraîné (TensorFlow) effectue des prédictions sur les données transformées. Un **LabelEncoder** est utilisé pour décoder les indices des classes en noms réels des formes des nanoparticules.

### 3. Bibliothèques Nécessaires
- **Numpy** : Pour les transformations mathématiques.
- **Scikit-learn** : Pour gérer le pipeline et les transformations.
- **TensorFlow** : Pour le modèle d'apprentissage profond.
- **Joblib** : Pour sauvegarder et charger le scaler et le LabelEncoder.
- **Dill** : Pour sauvegarder et charger le pipeline complet.

### 4. Utilisation du Pipeline sur de Nouvelles Données

#### 4.1. Charger le pipeline sauvegardé
Pour charger le pipeline préalablement sauvegardé, utilisez **Dill** avec la commande suivante :

```python
with open("pipeline_sh.dill", "rb") as f:
    loaded_pipeline = dill.load(f)
    predictions = loaded_pipeline.transform(X_input)

