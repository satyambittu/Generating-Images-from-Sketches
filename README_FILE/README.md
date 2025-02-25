
# Sketch to Face Project

This project implements a deep learning-based approach to map sketches to real images, utilizing a custom dataset and the PyTorch framework.

## Features
- **Custom Dataset Class**: Efficiently manages sketch, attribute, and real image data.
- **Data Preprocessing**: Includes image resizing and transformation pipelines.
- **Deep Learning Framework**: Built with PyTorch, supporting GPU acceleration.

## Dataset
The project relies on:
- A pickle file (`images_dict_3.pkl`) containing image data.
- A CSV file (`df_atributes_40_columns.csv`) providing attribute details.
- Images from the CelebA dataset (`img_align_celeba`).

## Installation

### Prerequisites
- Python 3.7 or higher
- CUDA support (optional, for GPU acceleration)

### Steps
1. Clone this repository.
2. Install the required Python libraries:

    ```bash
    pip install -r requirements.txt
    ```

    Example `requirements.txt`:
    ```text
    numpy
    pandas
    opencv-python
    torch
    torchvision
    pillow
    ```

3. Download the required datasets and place them in the following structure:
    ```
    project_root/
    ├── images_dict_3.pkl
    ├── df_atributes_40_columns.csv
    ├── img_align_celeba/  # Contains all real images
    ```

## Running the Code
1. Ensure the datasets are in place.
2. Launch the Jupyter Notebook or run the script:
    ```bash
    jupyter notebook final_notebook_of_project.ipynb
    ```

    or:

    ```bash
    python final_script.py
    ```

3. Modify the notebook/script as needed for specific experiments.

## Notes
- Ensure CUDA is enabled if using a GPU: `device = 'cuda' if torch.cuda.is_available() else 'cpu'`.
- This project was initially developed on Kaggle; adjust paths as necessary for local environments.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
