# Plant Disease Detection using CNN

This project aims to detect plant diseases using Convolutional Neural Networks (CNN). The application allows users to upload images of crops, and it predicts the disease affecting the crop based on the uploaded image.


## File Descriptions

- **`app.py`**: Main Flask application file.
- **`fastapi/app.py`**: Main FastAPI application file.
- **`app/main.py`**: Contains the Streamlit application and model prediction logic.
- **`app/class_indices.json`**: JSON file mapping class indices to class names.
- **`model`**: Directory containing the model weights.
- **`templates`**: HTML templates for the web interface.
- **`static`**: CSS files for styling the web interface.
- **`requirements.txt`**: List of dependencies required for the project.
- **`Notebooks`**: Jupyter notebooks for model training and experimentation.

## Project Structure

```
    .
    ├── .gitignore
    ├── fastapi/
    │   ├── __init__.py
    │   ├── app.py
    │   ├── class_indices.json
    │   ├── model/
    │   │   └── keras_model_weights.weights.h5
    │   ├── static/
    │   │   └── style.css
    │   └── templates/
    │       └── index.html
    ├── app/
    │   ├── class_indices.json
    │   ├── main.py
    │   ├── model/
    │   │   ├── Crop Disease Prediction model.h5
    │   │   └── keras_model_weights.weights.h5
    ├── app.py
    ├── Notebooks/
    │   └── Crop Disease Prediction.ipynb
    ├── README.md
    ├── requirements.txt
    ├── static/
    │   └── style.css
    ├── templates/
    │   └── index.html
    ├── test_images/

```


## Setup

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/crop-disease-detection.git
    cd crop-disease-detection
    ```

2. **Create a virtual environment:**
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the dependencies:**
    ```sh
    pip install -r requirements.txt
    ```

4. **Download the model weights and place them in the appropriate directory:**
    - Place `keras_model_weights.weights.h5` in `app/model/` and `fastapi/model/`.

5. **Run the Flask application:**
    ```sh
    python app.py
    ```

6. **Run the FastAPI application:**
    ```sh
    uvicorn fastapi.app:app --reload
    ```

## Usage

### Web Interface

1. **Flask Application**:
    - Open your browser and go to `http://127.0.0.1:5000`.
    - Upload an image of a crop.
    - Click on the "Predict" button to get the prediction.

2. **FastAPI Application**:
    - Open your browser and go to `http://127.0.0.1:8000`.
    - Upload an image of a crop.
    - Click on the "Predict" button to get the prediction.

### Streamlit Interface

1. **Run the Streamlit application**:
    ```sh
    streamlit run app/main.py
    ```
2. **Open your browser** and go to the URL provided by Streamlit (usually `http://localhost:8501`).
3. **Upload an image** of a crop.
4. **Click on the "Classify" button** to get the prediction.

### API Usage

1. **FastAPI Endpoints**:
    - **Upload Image and Predict**:
        ```sh
        POST /predict/
        ```
        - **Request Body**: Multipart form data with the image file.
        - **Response**: JSON object with the predicted class.
