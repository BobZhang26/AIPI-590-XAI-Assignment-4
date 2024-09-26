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

# 2.2 Boosted Stump
![image](https://github.com/user-attachments/assets/6b8d797c-5c56-4969-92c4-124776e22e67)

# 2.3 Hierarchical shrinkage wrapper
![image](https://github.com/user-attachments/assets/e4626df2-512b-491b-896b-db180434e528)
![image](https://github.com/user-attachments/assets/65bab5b6-cb85-4a44-8be8-475e7b65d562)





