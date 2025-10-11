# ExpressiveShift: Face Attribute Manipulation with a Variational Autoencoder

[![Python 3.12](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)](https://www.python.org/downloads/release/python-3120/)
[![PyTorch 2.3.0](https://img.shields.io/badge/PyTorch-2.3.0-red?style=for-the-badge&logo=pytorch)](https://pytorch.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 📝 Project Description

**ExpressiveShift** is a deep learning project that leverages a **Variational Autoencoder (VAE)** to manipulate facial attributes on the CelebA dataset. The project demonstrates how a VAE can learn a meaningful latent space representation of images, allowing for precise and controllable alterations of features like "smiling" or "wearing eyeglasses".

The core idea is to identify the **difference vector** in the latent space between images that possess a specific attribute and those that do not. This vector, when added to the latent representation of a new image, effectively "shifts" the image towards that desired attribute.

This project is a great example of applying a VAE to generative tasks and understanding its capabilities in handling high-dimensional image data.

---

## 🚀 How It Works

The VAE architecture consists of two main components:

- **Encoder**: Compresses a 128x128 face image into a 200-dimensional latent vector.
- **Decoder**: Reconstructs the image from the 200-dimensional latent vector.

The key to the **ExpressiveShift** method is the manipulation of the latent space:

1.  **Calculate the Average Latent Vectors**: The VAE encodes all images with and without a specific attribute (e.g., `Smiling`) to generate their respective average latent vectors.
2.  **Determine the Difference Vector**: The difference between the two average latent vectors is calculated. This vector represents the "essence" of the attribute.
3.  **Apply the Shift**: The difference vector is added to a new image's latent vector.
4.  **Generate the New Image**: The modified latent vector is passed through the decoder to produce an image with the new attribute.



---

## 🎨 Results

The project notebook includes several visualizations showcasing the effectiveness of the model. Below are a few examples of the manipulations performed on an unseen face image.

### **Adding a Smile**
The difference vector for "smiling" is calculated and applied to a neutral image, resulting in a subtle yet noticeable change in expression.


### **Adding Eyeglasses**
Similarly, a difference vector for "eyeglasses" is used to add glasses to a face that did not originally have them.


---

## ⚙️ Installation & Usage

### Prerequisites
To run the Jupyter notebook and replicate the results, you need the following dependencies:

-   **Python**: 3.12+
-   **PyTorch**: 2.3.0+
-   **torchvision**: 0.18.0+
-   **matplotlib**: 3.8.4+
-   **numpy**: 1.26.4+

### Steps to Run

1.  Clone this repository:
    ```bash
    git clone [https://github.com/Nishant2102/ExpressiveShift.git](https://github.com/Nishant2102/ExpressiveShift.git)
    ```

2.  Navigate to the project directory:
    ```bash
    cd ExpressiveShift
    ```

3.  (Optional but Recommended) Set up a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate
    ```

4.  Install the required libraries:
    ```bash
    pip install -r requirements.txt
    ```

5.  Launch the Jupyter Notebook:
    ```bash
    jupyter notebook
    ```

6.  Open and run the **`Model_on_Celeba.ipynb`** notebook to see the model being trained and used for face attribute manipulation.

---

## 📂 Repository Structure\

ExpressiveShift/

├── Model_on_Celeba.ipynb   # Main notebook with the VAE implementation and face manipulation logic

├── helper_data.py          # Utility functions for data loading, preprocessing, and calculating average faces

├── helper_plotting.py      # Utility functions for plotting and visualizing images and results

├── helper_train.py         # Utility functions for training the VAE model

├── helper_utils.py         # Utility functions for setting seeds and ensuring reproducibility

├── LICENSE                 # MIT License file

├── README.md               # This README file

└── requirements.txt        # List of Python dependencies



---

## 🤝 Contribution

Feel free to open an issue or submit a pull request if you have suggestions for improvements, bug fixes, or new features.

---

## 📄 License

This project is open-source and available under the **MIT License**. For more information, see the `LICENSE` file.

---

**Note:** The CelebA dataset is not included in this repository. You will need to download and configure it separately to run the notebook.
