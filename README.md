🔍 What is EngageNet?

EngageNet is a machine learning pipeline that predicts and analyzes social media image engagement by correlating visual content features with interaction metrics such as likes, shares, or total engagement.
EngageNet is a machine learning pipeline that predicts and analyzes social media image engagement by correlating visual content features with interaction metrics such as likes, shares, or total engagement. This hybrid approach combines structured data regression models with deep learning-based image classification (InceptionV3) to explore which visual elements may drive engagement. The goal is to support creators and brands in making data-informed content decisions.

🧠 Key Features
1)Predicts engagement from semantic segmentation percentage, fine-grained recognition scores, and similarity scores.

2)Evaluates and compares multiple regression models (Linear, Ridge, Lasso, SVR, etc.) for prediction accuracy.

3)Uses InceptionV3, a powerful CNN model trained on ImageNet, to extract high-level object labels from images.

4)Outputs interpretable regression equations for real-world insights.

Visualizes model performance using R² scores and plots.
5)
#🛠️ In-Depth Code Walkthrough
#📊 1. Data Preprocessing & Modeling
Dataset: An Excel file containing image analysis metrics and engagement scores.

->Features (X):

1)semantic_seg_perc: Proportion of segmented visual content (e.g., foreground/background balance).

2)max_fine_recog: A numeric value indicating object-level recognition or clarity.

3)similarity: Cosine similarity or visual distance from a reference/trending image set.

4)Target (y): total_engage — the numeric engagement score (e.g., likes + comments).

5)Trains 8 different models:

Linear, Polynomial, Ridge, Lasso, ElasticNet, Decision Tree, Random Forest, SVR

6)Evaluates them using:Mean Squared Error (MSE) andR² Score

7)Displays performance via horizontal bar chart.

📈 2. Model Interpretation
A function prints readable regression equations for Linear, Ridge, Lasso, and ElasticNet models.

Helps users understand feature influence on engagement score.

🧠 3. Image Classification with InceptionV3
1)Loads an image using tf.keras.preprocessing.

2)Resizes it to 299x299 and pre-processes it for InceptionV3.

3)Extracts top-5 ImageNet labels (e.g., “zebra”, “volcano”) with confidence scores.

4)Displays the original image alongside predictions.
