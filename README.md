
# fraud-detection-flask
## Team Information
**Team ID: LTVIP2026TMIDS65699**

**Team Lead:** Alluri Mounika – Model Development  
**Team Members:**
Arumalla Nandini – Data Preprocessing & Feature Engineering  

Rekha Sri Boyina – Model Training & Evaluation  

Gaddam Sravani Thriveditha – Testing, Deployment & Documentation  
## Project Summary
The Online Payments Fraud Detection System is a machine learning based web application developed to detect fraudulent online payment transactions using the XGBoost algorithm. The system analyzes transaction details such as transaction type, amount, sender balance, and receiver balance to classify transactions as legitimate or fraudulent.

The model is trained on historical transaction data and integrated into a Flask backend application to provide real time fraud prediction. The system performs data preprocessing, feature engineering, model training, and evaluation to ensure high accuracy with balanced precision and recall.

The web interface allows users to enter transaction details and instantly receive prediction results. This project demonstrates the practical implementation of machine learning in financial fraud detection and helps improve digital transaction security by reducing financial risks and false predictions.

## Technologies and Tools Used
Programming Language: Python
Machine Learning Algorithm: XGBoost
Machine Learning Library: Scikit-learn
Data Processing: Pandas
Numerical Computation: NumPy
Backend Framework: Flask
Frontend: HTML
Styling: CSS
Template Engine: Jinja2
Visualization: Matplotlib
API Testing: Postman
IDE: VS Code
Database: CSV Dataset

## Features

- **Real-time Fraud Detection**: Instantly classify transactions as fraudulent or legitimate
- **User-Friendly Web Interface**: Simple and intuitive HTML forms for transaction input
- **Machine Learning Powered**: Uses advanced ML model trained on payment transaction data
- **RESTful API**: Backend endpoints for prediction requests
- **Easy Deployment**: Ready to deploy on Heroku or other cloud platforms

## Project Structure

```
flask/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── payments.pkl          # Pre-trained ML model
├── Procfile.txt          # Heroku deployment configuration
├── README.md             # This file
└── templates/
    ├── home.html         # Home page template
    ├── predict.html      # Prediction form template
    └── submit.html       # Results display template
```

## Installation & Setup

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)

### Step 1: Clone or Download the Repository

```bash
cd online\ payments\ fraud\ detection/flask
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

## Usage

### Running the Application Locally

1. Ensure you're in the flask directory
2. Run the Flask application:
   ```bash
   python app.py
   ```
3. Open your web browser and navigate to:
   ```
   http://localhost:5000
   ```
4. Use the interface to:
   - View the home page
   - Click on "Predict" to access the prediction form
   - Enter transaction details
   - Submit to get fraud detection results

### Input Features

The model requires the following transaction features:

| Feature | Description |
|---------|-------------|
| **step** | Time step in the dataset |
| **type** | Transaction type (encoded numerical value) |
| **amount** | Transaction amount in monetary units |
| **oldbalanceOrg** | Sender's balance before transaction |
| **newbalanceOrig** | Sender's balance after transaction |
| **oldbalanceDest** | Receiver's balance before transaction |
| **newbalanceDest** | Receiver's balance after transaction |

## Model Details

- **Model File**: `payments.pkl`
- **Model Format**: Serialized Python pickle object
- **Input Features**: 7 numerical features
- **Output**: Binary classification (Fraud = 1, Not Fraud = 0)
- **Technology**: Trained using scikit-learn and XGBoost

## Dependencies

Key dependencies listed in `requirements.txt`:

- **Flask** (3.0.3): Web framework for building the application
- **NumPy** (1.26.4): Numerical computing library
- **scikit-learn** (1.4.2): Machine learning library
- **XGBoost** (2.0.3): Gradient boosting library
- **pandas** (2.1.4): Data manipulation library
- **Gunicorn** (21.2.0): WSGI HTTP Server for production
- **Werkzeug** (3.0.3): WSGI utilities and HTTP exception classes
- **Jinja2** (3.1.3): Template engine for Flask

## Deployment

### Deploy to Heroku

1. Ensure `Procfile.txt` is configured correctly
2. Initialize git repository (if not already done):
   ```bash
   git init
   ```
3. Deploy using Heroku CLI:
   ```bash
   heroku create your-app-name
   git push heroku main
   ```

## How It Works

1. User submits a transaction form with the required features
2. The Flask backend receives the POST request
3. Input features are converted to NumPy array
4. The pre-trained model makes a prediction
5. Result (Fraud/Not Fraud) is displayed to the user

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Home page |
| `/predict` | GET | Prediction form page |
| `/submit` | POST | Process transaction and return prediction |

## Troubleshooting

**Issue**: `FileNotFoundError: payments.pkl not found`
- **Solution**: Ensure the trained model file `payments.pkl` is in the same directory as `app.py`

**Issue**: Port 5000 already in use
- **Solution**: Change the port in `app.py` or kill the process using port 5000

**Issue**: Module import errors
- **Solution**: Run `pip install -r requirements.txt` to install all dependencies

## Future Enhancements

- Add more detailed prediction explanations
- Implement confidence scores
- Add batch prediction capability
- Create admin dashboard for model monitoring
- Implement model versioning

## License

This project is provided as-is for educational and research purposes.

## Support

For issues or questions, please check the application logs or review the Flask documentation at https://flask.palletsprojects.com/
