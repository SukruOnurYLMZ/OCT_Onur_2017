Transfer Learning Assignment: Custom CNN vs InceptionV3 Transfer Learning on OCT 2017 Dataset
📁 Dataset Description:
You will work with the OCT 2017 retinal image dataset, which consists of 84,484 optical coherence tomography (OCT) images, divided into the following four diagnostic classes:
• CNV (Choroidal Neovascularization)
• DME (Diabetic Macular Edema)
• DRUSEN
• NORMAL
You can find the dataset at: 👉 https://data.mendeley.com/datasets/rscbjbr9sj/3
🎯 Objective:
The goal of this assignment is to:
1. Build a custom Convolutional Neural Network (CNN) from scratch for multiclass classification.
2. Build a second model using InceptionV3 with transfer learning.
3. Compare the performance of both models and reflect on the impact of transfer learning.
🧪 Assignment Instructions:
✅ Part 1: Data Preparation
1. Download and extract the OCT2017 dataset (it contains folders: train/, test/, and val/).
2. Use ImageDataGenerator to:
o Rescale pixel values
o Optionally apply data augmentation on the training set
3. Print the class distribution in each folder to verify balance.
Tip: Make sure the images are resized to 150×150 for your custom CNN, and to 299×299 for InceptionV3 (its expected input size).
✅ Part 2: Build a Custom CNN Model
1. Create a Sequential model using the following suggested layers (you can modify as needed):
o Conv2D + MaxPooling2D (3–4 blocks)
o Flatten
o Dense + Dropout
o Output layer: Dense(4, activation='softmax')
2. Compile with:
o Loss: categorical_crossentropy
o Optimizer: adam
o Metrics: accuracy
3. Train for 10–15 epochs and validate using the val/ set.
4. Evaluate on the test/ set and record the final accuracy.
✅ Part 3: Apply Transfer Learning with InceptionV3
1. Import InceptionV3 from tensorflow.keras.applications, using include_top=False.
2. Freeze all base layers.
3. Add a custom classification head:
o GlobalAveragePooling2D
o Dense(128, activation='relu')
o Dense(4, activation='softmax')
4. Use the preprocess_input() function appropriate for InceptionV3.
5. Train and evaluate the model (same settings as above).
✅ Part 4: Visualization & Evaluation
1. Plot training vs validation accuracy and loss for both models.
2. Generate a confusion matrix and classification report on the test set for both models.
3. Record and compare:
o Accuracy
o Precision, Recall, F1-score
o Training time and convergence behavior
📊 Final Comparison
At the end of your notebook, create a summary table comparing:
Metric
Custom CNN
InceptionV3
Test Accuracy
Training Time
Validation Loss Trend
Improve/Falls/Rises
Overfitting Observed?
Yes/No
