## Pipeline de Prédiction des Nanoparticules: Pipeline Size

Ce pipeline permet de prédire la taille des nanoparticules à partir de données d'intensité mesurées.

### 1. Objectif du Pipeline
- **Entrée :** Signaux d'intensités des nanoparticules.
- **Sortie :** Prédictions de la taille des nanoparticules.

### 2. Étapes du Pipeline
- **Transformation Logarithmique :** Applique `np.log()` sur les intensités pour les rendre plus adaptées au modèle.
- **Normalisation des Données :** Utilise un scaler pré-entraîné pour standardiser les données.
- **Prédiction avec Modèle :** Un modèle pré-entraîné (TensorFlow) effectue des prédictions sur les données transformées.

### 3. Bibliothèques Nécessaires
- **Numpy** : Pour les transformations mathématiques.
- **Scikit-learn** : Pour gérer le pipeline et les transformations.
- **TensorFlow** : Pour le modèle d'apprentissage profond.
- **Joblib** : Pour sauvegarder et charger le scaler.
- **Dill** : Pour sauvegarder et charger le pipeline complet.

### 4. Utilisation du Pipeline sur de Nouvelles Données
1. **Charger le pipeline sauvegardé :**
   ```python
   with open("pipeline_size.dill", "rb") as f:
       loaded_pipeline = dill.load(f) #charger le pipeline
       predictions = loaded_pipeline.transform(X_input)

   
