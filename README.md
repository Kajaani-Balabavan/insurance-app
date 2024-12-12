# Insurance Charges Prediction Model

This repository contains a machine learning pipeline built with [PyCaret](https://pycaret.org/) and deployed using [FastAPI](https://fastapi.tiangolo.com/). The project predicts insurance charges based on customer data, including a new `sex` column, and provides a REST API for real-time predictions.

---

## 📂 Project Structure

- `insurance_prediction_model.ipynb`: Jupyter Notebook for creating and training the machine learning model using PyCaret.
- `insurance_prediction_model.py`: Python script for setting up the FastAPI server.
- `insurance_prediction_model.pkl`: Serialized machine learning model saved using PyCaret.
- `README.md`: Documentation for the project.
- `requirements.txt`: File listing the project dependencies.
- `.gitignore`: Specifies files and directories to be ignored by Git.
- `LICENSE`: License file for the project.

---

## 📊 Dataset

The dataset used is the `insurance` dataset available in PyCaret's built-in dataset library. It contains customer information such as:

- `age`: Age of the individual.
- `sex`: Gender of the individual (`male` or `female`).
- `bmi`: Body Mass Index.
- `children`: Number of children covered by health insurance.
- `smoker`: Smoking status (`yes` or `no`).
- `region`: Residential region of the individual.
- `charges`: Medical charges billed by the insurance company (target variable).

---

## 🔧 Setup and Installation

### Prerequisites

1. Conda installed on your system.
2. Python 3.9 or later.

### Installation Steps

1. Clone this repository:
   ```bash
   git clone https://github.com/Kajaani-Balabavan/insurance-app.git
   cd insurance-prediction
   ```

2. Create and activate a Conda environment:

   ```bash
   conda create --name pycaret_env python=3.9 -y
   conda activate pycaret_env
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Run the script to create the prediction model and start the FastAPI server:
   ```bash
   python insurance_prediction_model.py
   ```

---

## 🚀 How to Use

1. Start the FastAPI server by running `insurance_prediction_model.py`:

   ```bash
   python insurance_prediction_model.py
   ```

2. Open the interactive API documentation at `http://127.0.0.1:8000/docs`.

3. Use the `/predict` endpoint to make predictions.

### Example Request:

POST request to the `/predict` endpoint with JSON data:

```json
{
  "age": 30,
  "sex": "male",
  "bmi": 28.5,
  "children": 1,
  "smoker": "no",
  "region": "southeast"
}
```

### Example Response:

```json
{
  "prediction": 11234.75
}
```

---

## 🛠 Model Details

The model is built using PyCaret's regression module. The following steps are implemented:

1. Data preprocessing.
2. Automated model selection and evaluation using `compare_models()`.
3. The best model is serialized as `insurance_prediction_model.pkl`.
4. The model is deployed using FastAPI.

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

## 🙌 Acknowledgments

- Thanks to the [PyCaret Team](https://pycaret.org/) for their amazing library.
- The `insurance` dataset used is publicly available and built into PyCaret.

---
````
