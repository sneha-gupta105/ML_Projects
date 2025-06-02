Link to Jupyter Source File:
https://colab.research.google.com/drive/1SbhB44etW73efW6VqOgpBBwgwrn3foB8?usp=sharing


🧠 **Objective**
To develop a fraud detection system that:

Identifies potentially fraudulent insurance claims.

Combines textual claim descriptions and numerical/categorical features.

Provides intelligent claim summaries for human review using a language model.

🔍 **Dataset**
The dataset includes features such as:

Customer Demographics: Age, Occupation, Education, etc.

Policy & Claim Info: Claim amount, frequency, policy type, severity.

Text Data: Claim description.

Label: Fraud_Label (0 = Genuine, 1 = Fraudulent)

🛠️**Technologies Used**

Python

Pandas, Seaborn, Matplotlib

Scikit-learn (for ML pipeline and modeling)

Transformers (Hugging Face) (for summarizing claims)

Logistic Regression, Random Forest

TF-IDF Vectorization (for text features)

🔄 **Workflow**
1. Data Cleaning & Visualization
Visualized missing data via bar plots and heatmaps.

Dropped rows with missing values for modeling.

2. Exploratory Analysis
Analyzed distribution of fraud vs non-fraud claims.

Evaluated class balance.

3. Model 1: Logistic Regression
Built using a pipeline combining:

TF-IDF (text features)

StandardScaler (numeric features)

OneHotEncoder (categorical features)

Achieved baseline fraud detection performance.

4. Model 2: NLP-Only Model
Trained a standalone text-based logistic regression model using only Claim_Description.

5. Model 3: NLP + Random Forest
Combined all structured and unstructured data.

Trained using a RandomForestClassifier.

Evaluated model performance and identified uncertain predictions (for human review).

🧾 **Human-in-the-Loop Review**
Flagged claims with prediction confidence between 2% and 80% as "uncertain".

Summarized such claims using Phi-2 language model (microsoft/phi-2) to aid manual investigation.

Example Prompt
yaml
Copy
Edit
Summarize the following insurance claim for human review:
Customer Age: 45, Claim Amount: $1200, Policy Type: Auto, ...
📊** Results**
Model Accuracy: Displayed for each pipeline.

Classification Report: Includes precision, recall, F1-score.

Claims Needing Review: Summarized using LLM to assist human decision-making.

