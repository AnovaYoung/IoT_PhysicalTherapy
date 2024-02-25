**Machine Learning for IoT: Physical Therapy Exercise Classification and Prediction**

### Project Overview

This project leverages machine learning to enhance physical therapy through two main approaches: classifying types of physical therapy exercises from sensor data using a Convolutional Neural Network (CNN) model, and predicting future sensor readings with a time series prediction model.

### Dataset Description

The dataset used in this project contains rich time-series data captured from wearable MTx sensor units, each housing tri-axial accelerometers, gyroscopes, and magnetometers. The data encapsulate various physical therapy exercises performed by subjects, allowing the models to learn and recognize patterns in exercise execution.

### Models

## Physical Therapy Exercise Classifier

The first component of the project is a CNN model designed to classify the type of physical therapy exercise being performed. It processes the multi-dimensional sensor data, capturing the intricate motion patterns that characterize each exercise type.

**Data Preprocessing**
Segmentation: The sensor data were divided into uniform segments to form the input for the CNN, with padding for shorter segments and truncation for longer ones to maintain consistency.
Normalization: The sensor data were normalized to have a mean of zero and a standard deviation of one, aiding in the model's convergence and performance.
CNN Architecture
The CNN architecture is composed of convolutional layers for feature extraction, max-pooling layers for dimensionality reduction, and dense layers for classification. The output layer uses softmax activation to provide a probability distribution over the exercise types.

**Training and Validation**
The model was trained on 60% of the data, validated on 20%, and tested on the remaining 20%. It was evaluated based on accuracy, with plans to include a comprehensive analysis of precision, recall, and F1 scores for detailed performance metrics.

 ## Anomaly Detection Model

The second model in this project is focused on identifying anomalous behavior within sensor data using an Isolation Forest.

**Isolation Forest Model Setup**

- **Data Structuring**: Unlike models that require sequential data, the Isolation Forest algorithm works with unstructured data, analyzing each data point independently to determine its "anomalousness."
  
- **Feature Engineering**: Advanced approach to feature engineering was undertaken to enhance the model's ability to identify anomalous behavior within sensor data. Synthetic anomaly labels were crafted for each sensor reading and anomalies were synthetically labeled based on deviations from the norm. For each sensor axis, data points were marked as anomalies if they fell beyond a predefined threshold.

**Isolation Forest Architecture**

- The Isolation Forest model consists of numerous decision trees that isolate observations by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of the selected feature. Anomalies are those observations that have short paths on these trees, indicating they are easier to isolate from the rest of the data.

**Training and Evaluation**

- The Isolation Forest model was configured to estimate the level of contamination (proportion of outliers) in the dataset automatically. It was trained using the sensor data, with the goal of minimizing the false positive rate while maximizing the detection of true anomalies.
  
  ### Evaluation: The performance was assessed qualitatively in the absence of labeled data, through visual inspections. For quantitative analysis, synthetic anomaly labels were created based on statistical thresholds to measure the model's precision, recall, F1-score, and to plot Precision-Recall curves.

This anomaly detection approach allows for the efficient identification of outliers within the sensor data, providing valuable insights into potential issues or abnormal conditions without the need for pre-labeled training data.

### Results and Insights

The CNN classifier demonstrated a promising ability to differentiate between exercise types with an accuracy that improved across training epochs, suggesting that the model was learning meaningful patterns from the sensor data.
 
### Model Optimization:

Both models will undergo further tuning, including hyperparameter optimization, regularization, and potentially exploring alternative architectures to enhance performance.
Cross-Validation: Implementing k-fold cross-validation to ensure model stability and reliability across various data subsets.
Advanced Feature Engineering: Exploring more sophisticated time-series feature engineering techniques to improve model accuracy and robustness.
Model Interpretability: Investigating model decisions for both classifiers and predictors to gain insights into the factors driving predictions and classifications.

### Conclusion

This project stands at the intersection of IoT, machine learning, and healthcare, demonstrating the power of advanced analytical techniques to interpret sensor data and predict outcomes. The dual-model approach caters to both immediate classification needs and future event prediction, showcasing a comprehensive application of machine learning in a real-world context.


