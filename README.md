# **Project 1: Financial Sentiment Analysis with Reddit data & Data Processing**

## **Project Overview**
This project focuses on acquiring, cleaning, preprocessing, and analyzing financial text data for sentiment analysis and exploratory data analysis (EDA). The dataset is collected from **Reddit cryptocurrency discussions** using the **Reddit API**. The final deliverable includes processed datasets, code for data pipeline, exploratory insights, and feature engineering for further predictive modeling.

## **📂 Project Structure**
```
├── data_fetching.ipynb       # Jupyter Notebook for data acquisition, cleaning, and processing
├── csv_clean_bitcoin_1000.csv  # Cleaned dataset after preprocessing
├── csv_feature_engineered_bitcoin_1000.csv  # Feature-engineered dataset
├── Project_Report.pdf         # Final report summarizing methodology & insights
├── README.md                  # Project documentation (this file)
```

---

## **🔹 Data Acquisition**
### **✅ Source: Reddit API**
- Data is fetched from the **r/cryptocurrency** subreddit.
- **`praw`** library is used to extract posts mentioning Bitcoin.
- Extracted features:
  - **Title**: The title of the Reddit post
  - **Content**: The full post content
  - **Upvotes**: Number of upvotes on the post
  - **Comments**: Number of comments on the post
  - **Timestamp**: UNIX timestamp of post creation
  - **URL**: Link to the original post

### **📜 How to Fetch Data**
Ensure you have **Reddit API credentials** set up before running the script.
```bash
pip install praw
python data_fetching.ipynb
```

---

## **🔹 Data Cleaning & Preprocessing**
### **✅ Cleaning Steps**
- **Standardizing column names** (lowercase, removing spaces)
- **Removing special characters & URLs** from text
- **Handling missing values** (filling NaN in `content` with "No content")
- **Dropping duplicates** based on **URL & Title**
- **Converting timestamps** to datetime format

### **🔹 Exploratory Data Analysis (EDA)**
- **Visualizing upvotes & comments distribution**
- **Checking correlation between engagement & sentiment**
- **Time-series analysis of Bitcoin-related discussions**

---

## **🔹 Feature Engineering**
### **✅ Added Features**
| Feature | Description |
|---------|-------------|
| `title_len` | Number of words in the post title |
| `content_len` | Number of words in the post content |
| `is_working_hours` | Whether the post was made during business hours (9AM - 5PM) |
| `engagement_score` | Weighted score of upvotes & comments |
| `upvote_to_comment_ratio` | Ratio of upvotes to comments |
| `has_bitcoin` | Whether "Bitcoin" appears in the title |

### **✅ Sentiment Analysis**
- **VADER Sentiment Analyzer** applied to **title & content**
- **Labels**: Positive, Neutral, Negative

```bash
pip install vaderSentiment
python sentiment_analysis.py
```

---

## **🔹 Running the Project**
### **📦 Install Dependencies**
Ensure you have the required Python packages installed:
```bash
pip install praw pandas numpy seaborn matplotlib nltk vaderSentiment transformers
```

### **🚀 Running Data Pipeline**
1. **Fetch Data**
```bash
jupyter notebook data_fetching.ipynb
```
2. **Process & Clean Data**
```bash
jupyter notebook data_cleaning.ipynb
```
3. **Perform EDA & Feature Engineering**
```bash
jupyter notebook feature_engineering.ipynb
```

---

## **📌 Submission Guidelines**
### **📜 Deliverables**
1. **Dataset:**
   - `csv_clean_bitcoin_1000.csv`
   - `csv_feature_engineered_bitcoin_1000.csv`
2. **Code Files:**
   - `data_fetching.ipynb`
   - `feature_engineering.ipynb`
3. **Report:**
   - `Project_Report.pdf`
   - **GitHub Repository Link** (Public / Grant Access to `ap4347`)

📅 **Due Date: February 19th, 11:59PM**

🚀 **Make sure all files are uploaded to GitHub and the repository is accessible!**

