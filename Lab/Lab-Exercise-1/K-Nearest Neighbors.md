<!-- Background github cover with short introduction down below -->
<img src="https://github.com/flexycode/CCMACLRL_EXERCISES_COM231ML/blob/main/assets/Machine-Learning-BGCover1.png" />

# 🤖 K-Nearest Neighbors for Personality Classification

### 📖 Overview
This exercise demonstrates the implementation of K-Nearest Neighbors (KNN) algorithm to predict personality types (Introvert vs Extrovert) based on social media behavior patterns. I've learned to build a complete machine learning pipeline from data collection to model evaluation.

# 🎯 Learning Objectives
Through this exercise, I've learned:

* **Data preprocessing** and exploratory data analysis
* **Feature engineering** for social media behavioral data
* **Implementation** of K-Nearest Neighbors algorithm
* **Model evaluation** using multiple performance metrics
* **Real-world application** of machine learning for personality prediction

📊 Dataset Description
I've worked with a custom dataset containing 100 social media user samples with the following features:


### Features
| Feature | Description | Values |
|---|---|---|
| `Name` | User identifier | Text (removed during preprocessing) |
| `Posts/Share Frequently?` | Posting frequency behavior | 0 (Rarely), 1 (Frequently) |
| `Active?` | Platform activity level | 0 (Low activity), 1 (High activity) |
| `Replies to comments/messages?` | Social engagement level | 0 (Rarely replies), 1 (Often replies) |
| `Number of Friends/Followers` | Social network size | Numeric (50-5000) |
| `Personality` | Target variable | 0 (Introvert), 1 (Extrovert) |

---

### Dataset Statistics

* **Total samples**: 100
* **Features**: 4 (after removing Name column)
* **Classes**: 2 (Introvert, Extrovert)
* **Training set**: 80 samples (80%)
* **Test set**: 20 samples (20%)

### 🔄 Methodology

**1. Data Exploration**

I've performed comprehensive data analysis including:

```
# Dataset overview
df.head()
df.info()
df['Personality'].value_counts()

# Visualization
plt.hist(df['Number of Friends/Followers'], bins=20)
```

**2. Data Preprocessing**

```
# Remove non-predictive features
df = df.drop('Name', axis=1)

# Separate features and target
X = df.drop('Personality', axis=1).values
y = df['Personality'].values
```

**3. Train-Test Split**

```
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

**4. Model Training**

```
# Initialize KNN classifier
knn = KNeighborsClassifier(n_neighbors=5)

# Train the model
knn.fit(X_train, y_train)

# Make predictions
y_pred = knn.predict(X_test)
```

# 📈 Results and Performance
### Model Performance Metrics

Based on the implementation, I've achieved the following results:

### Model Performance
| Metric | Score | Description |
|---|---|---|
| `Accuracy` | `~85-90%` | Overall prediction correctness |
| `Precision` | `~80-85%` | Accuracy of positive predictions |
| `Recall` | `~85-90%` | Coverage of actual positives |
| `F1-Score` | `~82-87%` | Harmonic mean of precision and recall |

### Confusion Matrix
```
Predicted
            Introvert  Extrovert
Actual  
Introvert     8         2
Extrovert     1         9
```

### Key Insights I've Learned:

1. **Social media behavior patterns** are strong predictors of personality
2. **Active users** with high follower counts tend to be extroverts
3. **KNN performs well** on this type of behavioral classification problem
4. **Feature correlations** exist between posting frequency and personality type

### 🎯 Personal Predictions
I've tested the model with different personality profiles:
```
# Example predictions
test_cases = [
    [1, 1, 1, 3000],  # High activity → Extrovert
    [0, 0, 0, 200],   # Low activity → Introvert
    [1, 0, 1, 1500],  # Mixed profile → Varies
]

for case in test_cases:
    prediction = knn.predict([case])
    personality = 'Extrovert' if prediction[0] == 1 else 'Introvert'
    print(f"Profile {case} → {personality}")
```

### 🔍 What I've Learned
### Technical Skills Acquired:

* **Data Science Pipeline**: Complete workflow from data loading to model deployment
* **Feature Engineering**: Selecting and preparing relevant features for ML
* **Algorithm Implementation**: Understanding KNN mechanics and parameter tuning
* **Model Evaluation**: Using multiple metrics to assess performance
* **Python Libraries**: Proficiency with pandas, sklearn, matplotlib

### Machine Learning Concepts Need to Mastered:

* **Supervised Learning**: Training models with labeled data
* **Classification Problems**: Predicting categorical outcomes
* **Cross-Validation**: Proper train-test splitting techniques
* **Distance Metrics**: How KNN calculates similarity between samples
* **Overfitting Prevention**: Balancing model complexity and generalization

### Real-World Applications I've Discovered:

* **Social Media Analytics**: User behavior prediction
* **Marketing Segmentation**: Customer personality profiling
* **HR Analytics**: Personality-based team formation
* **Product Personalization**: Customizing user experiences

### 🛠️ Technologies Used

* **Python 3.x: Primary programming language
* **Google Colab**: Development environment
* **pandas**: Data manipulation and analysis
* **NumPy**: Numerical computations
* **scikit-learn**: Machine learning implementation
* **Matplotlib**: Data visualization
* **openpyxl**: Excel file handling

### 📁 File Structure
```
CCMACLRL_EXERCISES_COM243ML
├──
  Lab-Exercise-1/
  ├── Exercise1.ipynb         # Main Jupyter notebook
  ├── data.xlsx               # Dataset (100 personality samples)
  └── README.md               # This documentation
```

### 🚀 How to Run
1. **Clone the repository**:
```
git clone https://github.com/flexyledger/CCMACLRL_COM243ML.git
```
2. **Open Google Colab**:
* Navigate to [Google Colab](https://colab.google/)
* Upload the `Exercise1.ipynb` notebook
  
3. **Upload dataset**:
```
from google.colab import files
uploaded = files.upload()  # Select data.xlsx
```

4. **Install dependencies**:
```
!pip install openpyxl
```

5. **Run all cells** seqeuntially to reproduce the results


# 🤔 Future Improvements
Based on what I've learned, potential enhancements include:

* **Feature expansion**: Adding age, location, interests
* **Algorithm comparison**: Testing Random Forest, SVM, Neural Networks
* **Hyperparameter tuning**: Optimizing k-value and distance metrics
* **Cross-validation**: Implementing k-fold validation for robust evaluation
* **Feature scaling**: Normalizing numerical features for better performance

# 🎓 Conclusion
This exercise has provided me with a solid foundation in machine learning fundamentals. I've successfully implemented a personality classification system that demonstrates the practical application of KNN algorithm in social media analytics. The experience has equipped me with essential data science skills and deepened my understanding of how AI systems make predictions about human behavior.
The project showcases the power of machine learning in understanding human personality through digital footprints, which has significant applications in modern technology and business intelligence.

# 📞 Contact
For questions about this implementation or collaboration opportunities:

* **GitHub**: [@flexyledger](https://github.com/flexyledger)
* **Repository**: [CCMACLRL_COM243ML](https://github.com/flexyledger/CCMACLRL_COM243ML)

-----------------------------------------------------------------------------------
This exercise is part of the Computer Science Machine Learning course (COM243ML) laboratory activities.  


<p align="center">
<img src="https://readme-typing-svg.demolab.com/?lines=Thanks+For+Visiting+Enjoy+Your+Day+~!;" alt="mystreak"/>
</p>

<!-- Siero Miero 
<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3OGJ0aW80YnkwcjdmNzdzZ2tuMDdpaTZydzV5dTQ3M2VtdXlrd2k0ayZlcD12MV9zdGlja2Vyc19zZWFyY2gmY3Q9cw/iF7FoIWjpHD7E2ndx4/giphy.gif" width="300">
</div>
-->
<!-- End point line insert Comeback again next time, feel free to modify this  -->
<p align="center">
<img src="https://readme-typing-svg.demolab.com/?lines=Come+Back+Again+next+time" alt="mystreak"/>
</p>

</p>
    
