## UPI Fraud Mitigation With Machine Learning {[L@unch Live!](https://upi-fraud-mitigation-with-ml.netlify.app/)}

UPI Fraud Mitigation with Machine Learning is an innovative project aimed at safeguarding digital transactions in the growing Unified Payments Interface (UPI) ecosystem. With the increasing adoption of UPI, This project harnesses the power of machine learning to create a secure, intelligent system capable of detecting fraudulent transactions with a high accuracy. The project features a dynamic web interface for users to input transaction details and receive instant feedback, complemented by visual reports on transaction trends and fraud patterns.

### Project Structure:

```
upi-fraud-mitigation-with-machine-learning/
│
├── public/
│   ├── index1_intro-page.html       # Landing page introducing the project and its features.
│   ├── index2_login-page.html       # User login page to authenticate access to the system.
│   ├── index3_home-page.html        # Main user interface displaying system functionality & analytics.
│   ├── index4_entry-page.html       # Page for entering transaction details to check for fraud.
│   ├── index5_valid-page.html       # Confirmation page for transactions verified as legitimate.
│   ├── index6_invalid-page.html     # Warning page for transactions identified as fraudulent.
│   └── logincredentials_info.txt    # Sample login credentials for testing and demonstration purposes.
│
├── templates/
│   ├── index1.png(intro-page)       # Wireframe or screenshot of the introduction page.
│   ├── index2.png(login-page)       # Design template for the login page layout.
│   ├── index3.png(home-page)        # Image showing the design or layout of the dashboard.
│   ├── index4.png(entry-page)       # Visual guide for the data entry page structure.
│   ├── index5.png(valid-page)       # Image or mockup for the valid transaction confirmation view.
│   └── index6.png(invalid-page)     # Template for displaying the invalid transaction warning.
│
├── scripts/
│   ├── python.ipnyb                 # Jupyter Notebook for implementing fraud detection algorithms.
│   └── resultcheck.ipnyb            # Notebook for validating the results of fraud detection model.
│
├── data/
│   └── upitxnsdata.csv              # UPI transaction dataset for training, test, evaluate ML model.
│
├── README.md                        # Comprehensive guide to understanding, setting up the project.
├── .gitignore                       # Specifies files and directories to exclude from the repository.
└── LICENSE                          # Legal terms under which the project can be used, or modified.               
```

**UPI Fraud Mitigation Intro-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Intro.png)

**UPI Fraud Mitigation Login-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Login.png)

**UPI Fraud Mitigation Home-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Home.png)

**UPI Fraud Mitigation Entry-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Entry.png)

**UPI Fraud Mitigation Valid-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Valid.png)

**UPI Fraud Mitigation Invalid-page**

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Invalid.png)

### Technologies Used:

1.**Programming Languages:** Python.  
2.**Web Development:** HTML, CSS, JavaScript, Flask(or)Django.  
3.**Machine Learning Frameworks:** Scikit-learn, TensorFlow.  
4.**Machine Learning Libraries:** Pandas, NumPy.  
5.**Databases:** MongoDB, MySQL, SQLite.  
6.**APIs/Testing:** UPI API Integration, PyTest, UnitTest.  
7.**Data Sources:**  
- Real-time or simulated UPI transaction data.  
- Fraud datasets from sources like Kaggle or custom-labeled datasets.

### Installation and Usage Instructions:

1.**Clone the Repository:**
```
git clone https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning.git
cd Upi-fraud-mitigation-with-machine-learning
```
2.**Set Up a Python Virtual Environment:**
```
python3 -m venv venv     # Create virtual environment
source venv/bin/activate # Activate (Linux/macOS)
venv\Scripts\activate    # Activate (Windows)
```
3.**Install Required Libraries:**
```
pip install -r requirements.txt
```
4.**Ensure Data File is Present:** 
- upi_txnsdata.csv should be in the main directory.
5.**Run Jupyter Notebooks:**
```
jupyter notebook
```
- In the web browser, open python.ipynb and resultcheck.ipynb, and execute the cells.
6.**Run the Web Interface:**
- Method 1: Open HTML Files Directly: 
Navigate to the public folder and open the HTML files in your web browser.
- Method 2: Using a Simple HTTP Server:
```
cd Upi-fraud-mitigation-with-machine-learning/public
python3 -m http.server   # For Python 3
python -m SimpleHTTPServer   # For Python 2
```
- Open http://localhost:8000 in your web browser.
7.**Important Security Note:**
- Login Credentials: Found in logincredentials_info.txt.
**File Descriptions**
- public/index*.html: Web interface HTML/CSS/JavaScript files.
- public/logincredentials_info.txt: Contains login credentials.
- templates: Folder for HTML templates like logos and images.
- python.ipynb: Core machine learning model code.
- resultcheck.ipynb: Model evaluation code.
- upi_txnsdata.csv: Dataset for training and testing.



  


