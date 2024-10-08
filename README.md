[![Python Application Test with Github Actions](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml/badge.svg)](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml)
## AIPI-590-XAI-Assignmnet-4: Explainable Models
### Instructions
imodels is an interpretability library in python that has support for many decision rule set and list algorithms (https://github.com/csinva/imodels?tab=readme-ov-file). 

From the list of supported models available in the README (link above), choose three algorithms to demo on a dataset of your choice. 

In addition to a demonstration for each of your chosen algorithms, you should provide an explanation of the method via a visual. This visual can be a block diagram, a slide, or anything of your choosing. It should represent the method in a way that your fellow students would be able to understand the algorithm visually.

# 1. Loading Dataset
The Breast Cancer dataset is a commonly used dataset in machine learning and statistical research for binary classification tasks. It is part of the sklearn.datasets module in Scikit-learn and is often used for tasks like classification, model evaluation, and feature analysis. The dataset includes features derived from digitized images of fine needle aspirates (FNA) of breast masses, describing characteristics of the cell nuclei present in the images.


	•	Goal: The goal is to predict whether a breast tumor is benign or malignant based on various features extracted from breast mass images.
	•	Type: Supervised learning, Binary classification.
	•	Target Labels:
	•	0: Malignant (cancerous).
	•	1: Benign (non-cancerous).
	The dataset contains 30 numerical features that describe characteristics of cell nuclei present in the image. These features are computed for each cell nucleus and include:

	1.	Mean Radius: The average size of the cell nucleus.
	2.	Mean Texture: Variability in gray-scale intensity of the image.
	3.	Mean Perimeter: The average perimeter of the cell nucleus.
	4.	Mean Area: The average area of the cell nucleus.
	5.	Mean Smoothness: Local variation in the radius lengths.
	6.	Mean Compactness: Combination of perimeter² / area - 1.
	7.	Mean Concavity: Severity of concave portions of the contour.
	8.	Mean Concave Points: Number of concave portions of the contour.
	9.	Mean Symmetry: Symmetry of the cell nucleus.
	10.	Mean Fractal Dimension: Coastline approximation - 1.
Shape of the Dataset:

	•	Number of Samples (n_samples): 569
	•	Number of Features (n_features): 30
	•	Number of Classes (n_classes): 2 (Malignant, Benign)

# 2.1 Rulefit Classifier
```python
# initialize RuleFitRegressor and fit the training data
clf = RuleFitClassifier() # Use OneVsRestClassifier for multiclass
clf.fit(X_train, y_train)
```
```
X1: mean radius
X2: mean texture
X3: mean perimeter
X4: mean area
X5: mean smoothness
X6: mean compactness
X7: mean concavity
X8: mean concave points
X9: mean symmetry
X10: mean fractal dimension
X11: radius error
X12: texture error
X13: perimeter error
X14: area error
X15: smoothness error
X16: compactness error
X17: concavity error
X18: concave points error
X19: symmetry error
X20: fractal dimension error
X21: worst radius
X22: worst texture
X23: worst perimeter
X24: worst area
X25: worst smoothness
X26: worst compactness
X27: worst concavity
X28: worst concave points
X29: worst symmetry
X30: worst fractal dimension
```
<img width="1601" alt="Screenshot 2024-09-25 at 22 22 04" src="https://github.com/user-attachments/assets/4c59edd9-7d82-478b-8841-e70173e9cd21">

# 2.2 Boosted Stump
```python
# fit boosted stumps
# get feature names from load_breast_cancer
feat_names = load_breast_cancer.feature_names
brc = BoostedRulesClassifier(n_estimators=10)
brc.fit(X_train, y_train, feature_names=feat_names)

# look at performance
probs = brc.predict_proba(X_test)
demo_helper.viz_classification_preds(probs, y_test)

```
![image](https://github.com/user-attachments/assets/6b8d797c-5c56-4969-92c4-124776e22e67)

# 2.3 Hierarchical shrinkage wrapper
```python
# fit the model
HSTC = HSTreeClassifierCV(max_leaf_nodes=7)  # initialize a model
HSTC.fit(X_train, y_train)   # fit model
preds = HSTC.predict(X_test) # discrete predictions: shape is (n_test, 1)
preds_proba = HSTC.predict_proba(X_test) # predicted probabilities: shape is (n_test, n_classes)

# visualize the model
plot_tree(HSTC.estimator_, feature_names=feat_names)
# look at performance
probs = HSTC.predict_proba(X_test)
demo_helper.viz_classification_preds(probs, y_test)
```
![image](https://github.com/user-attachments/assets/e4626df2-512b-491b-896b-db180434e528)
![image](https://github.com/user-attachments/assets/65bab5b6-cb85-4a44-8be8-475e7b65d562)





