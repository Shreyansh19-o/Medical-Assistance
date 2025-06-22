Disease Prediction System 🩺💡

This is a Python Flask web application that leverages machine learning to predict potential diseases based on user-provided symptoms. Beyond just predicting, it offers comprehensive information about the predicted disease, including its description, necessary precautions, recommended medications, dietary advice, and even suggested workouts.

✨ Features

Symptom-Based Disease Prediction: Input a list of symptoms to get an instant disease prediction.
Disease Description: Detailed information about the predicted disease.

Precautionary Measures: Get a list of precautions to take for the identified illness.

Medication Recommendations: Suggested medications for the predicted disease.

Dietary Advice: Specific diet recommendations to aid recovery or management.

Workout Suggestions: Relevant workout routines (if applicable) for the predicted condition.

Intuitive Web Interface: A simple and user-friendly web interface for input and results.

🚀 How it Works

The core of this system is a machine learning model (specifically a Support Vector Classifier, SVC) trained on a dataset linking symptoms to diseases.

Data Loading: The application loads several CSV files containing symptom descriptions, precautions, workouts, general disease descriptions, medications, and diets.

Model Loading: A pre-trained svc.pkl model is loaded, which is responsible for making the disease predictions.

Symptom Mapping: When a user inputs symptoms, they are converted into a numerical vector (based on a predefined symptom dictionary symptoms_dict) that the machine learning model can understand.

Prediction: The SVC model takes this symptom vector as input and predicts the most likely disease.

Information Retrieval: Based on the predicted disease, the helper function retrieves associated descriptions, precautions, medications, diets, and workouts from the loaded datasets.

Display Results: The predictions and relevant information are then rendered on the web page.

🗃️ Datasets Used
The application relies on several CSV files, which should be placed in a dataset/ directory:

symtoms_df.csv: Likely contains the training data with symptoms mapped to disease IDs.

precautions_df.csv: Lists precautions for various diseases.

workout_df.csv: Provides workout suggestions per disease.

description.csv: Contains textual descriptions of diseases.

medications.csv: Lists medications for diseases.

diets.csv: Provides diet recommendations for diseases.

🛠️ Setup and Installation

1. Prerequisites
Python 3.x

Git (optional, for cloning the repository)

2. Project Structure
Ensure your project directory is organized as follows:

.
├── app.py
├── models/
│   └── svc.pkl
├── dataset/
│   ├── symtoms_df.csv
│   ├── precautions_df.csv
│   ├── workout_df.csv
│   ├── description.csv
│   ├── medications.csv
│   └── diets.csv
├── templates/
│   ├── index.html
│   ├── About.html
│   ├── Contact.html
│   └── Symptoms.html
├── static/ (if you have CSS/JS/images)
│   └── ...
└── README.md

3. Clone the Repository (or download files)
If you have Git:

git clone https://github.com/your-username/disease-prediction-system.git
cd disease-prediction-system

(Replace your-username with your actual GitHub username or the repository URL if applicable)

4. Install Dependencies
It's highly recommended to use a Python virtual environment to manage dependencies.

# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
.\venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install required Python packages
pip install Flask numpy pandas scikit-learn

5. Obtain Model and Dataset Files
The svc.pkl model file and all .csv dataset files (from the dataset/ directory mentioned above) are crucial for the application to run. You will need to source these if they are not included in the repository. Typically, these would be provided alongside the app.py script.

6. Create templates/ and static/ directories
Ensure you have a templates folder in the same directory as app.py containing index.html, About.html, Contact.html, and Symptoms.html.

If your application uses static assets (CSS, JavaScript, images), ensure you also have a static folder.

🚀 Running the Application

Activate your virtual environment (if not already active):

# On Windows:
.\venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

Navigate to the project root directory (where app.py is located).

Run the Flask application:

python app.py

The application will start, and you will see a message in your terminal indicating the address where it's running (e.g., http://127.0.0.1:5000/).

Open your web browser and navigate to that address.

🖥️ Usage

Home Page (/ or /predict): This is where you will input your symptoms.

Enter your symptoms (e.g., itching, skin_rash, fatigue) into the input field. Ensure symptoms are comma-separated and correctly spelled as per the symptoms_dict in app.py.

Click the "Predict" button.

The page will display the predicted disease along with its description, precautions, medications, diet, and workout recommendations.

About Page (/About): Access information about the project or its creators.

Contact Page (/Contact): Find contact details.

Symptoms Page (/Symptoms): Likely displays a list of available symptoms for reference.

