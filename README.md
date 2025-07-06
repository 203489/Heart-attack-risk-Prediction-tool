📊 Input Variables
The model uses the following input features:

Age

Gender

Blood Pressure

Cholesterol

Fasting Blood Sugar

Resting ECG Results

Max Heart Rate Achieved

Exercise Induced Angina

ST Depression

Number of Major Vessels

Thalassemia

Medical History (optional columns)

🧠 Models Used
Logistic Regression

Random Forest Classifier

Gradient Boosting Classifier

Each model contributes to an ensemble decision-making process to improve accuracy and generalizability.

📤 Output
The script exports an Excel file that includes:

Patient ID

Individual risk score (probability)

Risk category (Low, Moderate, High)

Final prediction

Model confidence

Summary statistics (in a separate sheet)

🚀 How to Run
Step 1: Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
Step 2: Run the Python script
bash
Copy
Edit
python app.py
Make sure your input Excel file is correctly placed in the data/ folder.

📈 Sample Visuals
ROC Curve for each model

Confusion Matrix

Feature Importance Chart
(Automatically saved in the visuals/ folder)

📌 Project Status
🔬 This project is part of a broader study titled:
"Advanced Machine Learning for Heart Attack Risk Prediction: A Case Study on Integrating Patient Demographics, Medical History, and Lifestyle Factors at Maro Medical Center."

It is under ongoing refinement and may later include a web interface and RESTful API.

👨‍⚕️ Acknowledgements
Special thanks to Maro Medical Center for anonymized datasets and the support of the clinical research team.

📜 License
This project is licensed for academic and non-commercial use. For commercial applications, please contact the author.

