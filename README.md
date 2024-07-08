# PROJECT SUMMARY

Image classification plays a pivotal role in indexing and organizing the insane amount of images that exist on the internet so that they can be easily used by individuals and organizations alike. I completed the following task as part of my Prodigy InfoTech machine learning internship. Some of the insights I derived from the project are:
Image classification plays a pivotal role in organizing and indexing the insane amount of images that exist on the internet so that they can be easily used by individuals and organizations alike. I completed the following task as part of my Prodigy InfoTech machine learning internship. Some of the insights I derived from the project are:

- Google Colab provides an interactive workspace for data science & ML tasks
- Google Colab also seamlessly integrates with Google Drive which is useful for working with large visual datasets
@@ -9,7 +9,7 @@ Image classification plays a pivotal role in indexing and organizing the insane
- GridSearchCV is an extremely useful tool for hyperparameter tuning, epecially for SVMs where C and gamma values significantly affect model outcomes
- Setting the parameter verbose=3 for model fitting helps one track the model training time which exponentially increases with number of samples and features
- Having a good command of numpy functions saves a lot of time when feature engineering
- Deleting redundant arrays and performing garbage collection significantly reduces memory footpring
- Deleting redundant arrays and performing garbage collection significantly reduces memory footprint

# NOTEBOOK SUMMARY

1. Data Acquisition
I downloaded the following Kaggle dataset: https://www.kaggle.com/c/dogs-vs-cats/data and uploaded the zip folder to my Google Drive under Colab Notebooks section. I used Zipextractor to unpack its folders within Google Drive but I used shutil to unpack the train dataset onto my session storage in Google Colab. I used regular expression matching on the files to separate cat and dog images and applied skimage tools to visualize them.
2. Data Preprocessing
The preprocessing steps were converting the rgb image to grayscale, applying Gaussian smoothing and Laplace operator for edge detection, and resizing the image and flattening its array to suit the model fitting process. Applying np.vstack to an empty features array and later np.append more features was useful for reducing memory footprint. I then used explained variance score to determine minimum number of features that were needed from the image arrays and used it to perform principal component analysis on the entire feature set.
3. Model Training
Sklearn's train_test_split were useful for shuffling the features and labels and dividing them into training and test sets. I set its stratify parameter to the labels to ensure balanced class distribution in both the training and test sets. I used to GridSearchCV to defined 3 C and 3 gamma values. However, different values should still be tried in the future. For the SVC's kernel I chose to only try rbf since its optimal for image classification and trying other kernels would significantly increase the model training time. I also set the GridSearchCV verbose parameter to 3 to print the scores and time for each model fit enabling time tracking. I then used joblib to save the model and avoid redundant training processes.
4. Model Evaluation
I used Sklearn's accuracy_score (model accuracy), classification_report (precision, recall, and f1-score), and confusion_matrix (true positives, true negatives, false positives, etc.). I then unpacked test dataset from the Kaggle dataset to apply the model to new data. For each image I applied the preprocessing steps I had previously applied to the train dataset and printed its model prediction class and probability scores for each class.
