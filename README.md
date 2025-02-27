# Malaria Detection Model

## Overview
This project presents a deep learning model for classifying blood smear images as either uninfected or parasitized using TensorFlow. The model has been successfully developed and trained to detect malaria-infected cells with high accuracy.

## Project Description
Malaria is a life-threatening disease caused by parasites that are transmitted to people through the bites of infected mosquitoes. Early detection and diagnosis are crucial for effective treatment. This project utilizes deep learning techniques to automate the classification of blood smear images, providing a fast and reliable method for malaria detection.

### Key Features
- Developed using TensorFlow and Keras.
- Trained on a dataset of blood smear images to classify between uninfected and parasitized cells.
- Pretrained model available for testing on unseen datasets.

## Dataset
The dataset consists of microscopic blood smear images categorized into two classes:
1. **Uninfected** - Blood smear images that do not contain malaria parasites.
2. **Parasitized** - Blood smear images that contain malaria parasites.

The dataset was preprocessed to enhance model performance, including image augmentation, normalization, and resizing to ensure consistency.

## Model Training
The model was trained using Google Colab with TensorFlow and Keras. The training process involved:
- **Data Augmentation:** To improve generalization and reduce overfitting.
- **Convolutional Neural Networks (CNNs):** Used to extract features from the images.
- **Optimization Techniques:** Adam optimizer was used for efficient convergence.
- **Evaluation Metrics:** Accuracy, precision, recall, and F1-score were used to assess the model's performance.

## Pretrained Model
A pretrained version of the model is available for immediate use. The trained model is saved as `malaria.keras` and can be loaded for inference on new datasets.

### Download the Pretrained Model
You can download the trained model from the following link:
[malaria.keras](https://drive.google.com/file/d/1iOXgYb-MtYlXUTV50Sk9hbfXDeX8HeGn/view?usp=sharing)

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/brunoadul/malaria.git
   cd malaria-classification
   ```
2. Install required dependencies:
   ```bash
   pip install tensorflow numpy pandas matplotlib
   ```
3. Load and test the pretrained model:
   ```python
   from tensorflow.keras.models import load_model
   import numpy as np
   from tensorflow.keras.preprocessing import image

   # Load the trained model
   model = load_model('malaria.keras')

   # Load an image for testing
   img_path = 'path_to_test_image.jpg'
   img = image.load_img(img_path, target_size=(150, 150))
   img_array = image.img_to_array(img)
   img_array = np.expand_dims(img_array, axis=0)
   img_array /= 255.0  # Normalize

   # Make a prediction
   prediction = model.predict(img_array)
   print('Uninfected' if prediction < 0.5 else 'Parasitized')
   ```

## Future Improvements
- Enhance the dataset by incorporating more diverse samples.
- Experiment with different deep learning architectures to improve accuracy.
- Deploy the model as a web or mobile application for real-world usability.

## Contributors
- brunoadul
- brunoadul@gmail.com

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

