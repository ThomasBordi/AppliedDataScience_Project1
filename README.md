# **AppliedDataScience_Project 1**
## **Reddit financial data Sentiment Analysis & Data preparation**

## **Project Overview**
This project focuses on acquiring, cleaning, preprocessing, and analyzing financial text data for sentiment analysis and exploratory data analysis (EDA). The dataset is collected from Reddit cryptocurrency discussions using the Reddit API. The final deliverable includes processed datasets, code for data pipeline, exploratory insights, and feature engineering for further predictive modeling.

## **📂 Project Structure**
```
├── data_pipeline.ipynb       # Jupyter Notebook for data acquisition, cleaning, and processing
├── csv_bitcoin_1000.csv      # Reddit dataset acquired from Reddit API
├── csv_clean_bitcoin_1000.csv  # Cleaned dataset after preprocessing
├── csv_feature_engineered_bitcoin_1000.csv  # Feature-engineered dataset
├── Project_Report.pdf         # Final report summarizing methodology & insights
├── README.md                  # Project documentation
├── requirement.txt           # Packages requirement
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
python data_pipeline.ipynb
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
- **Checking correlation between engagement & text feature**
- **Time-series analysis of Bitcoin-related discussions**

---

## **🔹 Data Preprocessing & Feature Engineering**
### **✅ Added Features**
| Feature | Description |
|---------|-------------|
| `log_upvotes` | Log transformation of upvotes because of right skewed distribution |
| `log_comments` | Log transformation of comments because of right skewed distribution |
| `title_len` | Number of words in the post title |
| `content_len` | Number of words in the post content |
| `is_working_hours` | Whether the post was made during business hours (9AM - 5PM) |
| `engagement_score` | Weighted score of upvotes & comments |
| `upvote_to_comment_ratio` | Ratio of upvotes to comments |
| `has_bitcoin` | Whether "Bitcoin" appears in the title |

---

## **🔹 Running the Project**
### **📦 Install Dependencies**
Ensure you have the required Python packages installed:
```bash
pip install -r requirements.txt
```

### **🚀 Running Data Pipeline**
```bash
jupyter notebook data_pipeline.ipynb
```

