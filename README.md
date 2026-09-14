# Assignment 11: Image Classification Using Random Forest

## Overview

This project focuses on image classification using a Random Forest Classifier. The aim was to train a machine learning model that could classify images into different categories after applying basic image preprocessing.

The dataset contained images from five classes:

* Dalmatian
* Dollar Bill
* Pizza
* Soccer Ball
* Sunflower

The images were processed and used to train and evaluate a Random Forest classification model.

## Dataset and Preprocessing

The images had different sizes, so they were first converted to RGB format and resized to **64 × 64 pixels**.

The pixel values were normalized by dividing them by 255 so that the values were between 0 and 1.

Each image was then flattened into a single feature vector. Since each image had 64 × 64 pixels and 3 RGB channels, each image produced 12,288 numerical features.

The dataset was divided into:

* 80% training data
* 20% testing data

A stratified split was used to maintain the class distribution between the training and testing sets.

## Random Forest Model

A Random Forest Classifier was used for the main classification task.

GridSearchCV was used to find suitable hyperparameters. The parameters tested included:

* `n_estimators`
* `max_depth`
* `min_samples_split`
* `min_samples_leaf`

A total of 16 parameter combinations were tested using 3-fold cross-validation, resulting in 48 model fits.

The best parameters found were:

```text
n_estimators = 100
max_depth = None
min_samples_split = 5
min_samples_leaf = 1
```

The best cross-validation accuracy was approximately **77.73%**.

## Model Evaluation

The final Random Forest model was evaluated on 62 test images.

The results were:

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 75.81% |
| Precision | 75.72% |
| Recall    | 75.81% |
| F1-score  | 75.33% |

The model performed best on the sunflower class, which had a recall of 94%. The pizza class was more difficult for the model, with a recall of 60%.

## Confusion Matrix

The confusion matrix was used to examine the correct and incorrect predictions for each image class.

The model correctly classified 47 out of the 62 test images. Some confusion occurred between classes such as dalmatian and soccer ball, while sunflower images were classified more successfully.

## Feature Importance

Random Forest provides feature importance values that show which input features contributed more to the model's decisions.

Since the images were flattened, the features represent pixel positions in the image. The most important feature in this experiment was Pixel 5117, followed by several other pixel features.

The top 20 important image features were visualized using a bar chart in the notebook.

## Prediction on a New Image

A prediction function was created using the same preprocessing steps used during training.

A new image named:

```text
new pizza.jfif
```

was uploaded and tested.

The model predicted:

```text
Predicted Class: pizza
```

This showed that the trained model could also be used to make predictions on a new image.

## Tools and Technologies

The project was completed using:

* Python
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Pillow (PIL)
* Scikit-learn
* Random Forest
* GridSearchCV

## How to Run the Project

1. Open the Jupyter Notebook in Google Colab.
2. Upload the `images.zip` dataset when prompted.
3. Run the notebook cells from top to bottom.
4. The notebook extracts and preprocesses the images.
5. The Random Forest model is trained using GridSearchCV.
6. The model is evaluated using accuracy, precision, recall, F1-score, confusion matrix, and classification report.
7. Feature importance is visualized.
8. A new image can be uploaded to test the trained model.

## Project Files

* `Assignment_11_Image_Classification_Random_Forest_OBAJE_PAUL.ipynb` – Google Colab/Jupyter Notebook containing the complete analysis and model.
* `Assignment_11_Image_Classification_Random_Forest_OBAJE_PAUL.pdf` – PDF report containing the methodology, results, visualizations, and conclusion.
* `README.md` – Project overview and instructions.

## Conclusion

This project demonstrated how Random Forest can be applied to image classification after converting images into numerical features. The final model achieved 75.81% accuracy on the test set and successfully predicted a new pizza image as pizza.

The results also showed that image classification can be affected by the quality and representation of the image features. Further improvements could be achieved by using a larger dataset or image-specific deep learning methods such as Convolutional Neural Networks.

## Author

**OBAJE PAUL**

**Course:** MACHINE LEARNING
