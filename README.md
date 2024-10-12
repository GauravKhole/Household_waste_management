# Household_waste_classification_using_CNN
# Overview
This project aims to build a Household Waste Classification using Convolutional Neural Network(CNN). The system classifies household waste into 29 different categories using a deep learning model. The goal is to facilitate the automatic sorting and recycling of waste. The model is deployed using a Streamlit interface, allowing users to upload images of waste items and receive instant predictions on their category and recyclability.

# Data Collection
Categories: 29 household waste categories.
Images: 700-1200 images per category.

# Waste Categories:
AEROSOL CANS, ALUMINUM FOOD CAN, ALUMINUM SODA CAN, CARDBOARD BOX, CLOTHES, COFFEE GROUND, DISPOSABLE PLASTIC CUTLERY, EGGSHELL, FOOD WASTE, GLASS BEVERAGE BOTTLE, GLASS COSMETIC CONTAINERS, GLASS FOOD JAR, MAGAZINES, NEWSPAPER, OFFICE PAPER, PAPER CUP, PLASTIC CUP LID, PLASTIC DETERGENT BOTTLE, PLASTIC FOOD CONTAINER, PLASTIC SHOPPING BAG, PLASTIC SODA BOTTLE, PLASTIC STRAW, PLASTIC TRASH BAG, PLASTIC WATER BOTTLE, SHOES, STEEL FOOD CANS, STYROFOAM CUPS, STYROFOAM FOOD CONTAINERS, TEA BAGS.

# Data Cleaning:
Removed dodgy images.
Filtered out images smaller than 5 KB.
Only kept images with extensions .jpeg, .jpg, .bmp, and .png.

# Data Preprocessing
*Image Resizing:* All images resized to 128x128 pixels for uniformity.

*Data Augmentation:* Applied techniques like shear, zoom, and horizontal flips to increase dataset variety.

*Normalization:* Rescaled pixel values to the range [0, 1] for better model performance using ImageDataGenerator.
Model Selection and Training

*Base Model:* MobileNetV2, a lightweight deep learning model pre-trained on ImageNet, was chosen for its balance between accuracy and speed.

*Custom Layers:*
Added GlobalAveragePooling2D to reduce dimensionality.
Added a dense layer with 512 neurons and ReLU activation for classification.
A Dropout layer was used to prevent overfitting.
The final dense layer has 29 neurons with softmax activation for multi-class classification.

*Optimizer and Loss Function:*

*Optimizer:* Adam

*Loss Function:* Categorical Cross-Entropy
Trained with early stopping to prevent overfitting.

# Model Evaluation

*Metrics:* Accuracy was the primary metric used during training.

*Validation:* A validation set was used to monitor model generalization across epochs.

*Performance:* MobileNetV2 was selected for its trade-off between inference speed and accuracy, which is crucial for real-time deployment.

# Deployment

*Interface:* The model is deployed using a Streamlit interface, allowing users to upload an image of waste. The system predicts the waste category and whether it is recyclable.

*Backend:* The trained MobileNetV2 model is loaded in the Streamlit app, where the image is preprocessed and classified.
