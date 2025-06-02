# Bank Marketing Campaign Analysis - SQL Project
## 📌 Overview
This project analyzes the effectiveness of a bank's marketing campaigns for term deposit subscriptions using synthetic data. The analysis identifies high-value customer segments, optimal campaign channels, and economic factors influencing success rates.

## 🛠️ Technologies Used
- **Database**: MySQL
- **Data Generation**: Python (Faker, Pandas)
- **Visualization**: Matplotlib/Seaborn (or specify if you used Tableau/Power BI)
- **Version Control**: Git/GitHub

## 📂 Dataset
Synthetic dataset containing:
- **10,000 customers** with demographic information
- **20 marketing campaigns** across 5 channels
- **Financial indicators** for each customer
Dataset generated with realistic distributions for:
   ****Customers Table**** - Customer age, occupation, education
   ****Campaigns Table**** - Campaign types (email, telemarketing, etc.)
   ****Financials Table**** - Economic factors (employment rate, consumer confidence)

## 📊 Data Dictionary

### Customers Table
| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| customer_id | Unique identifier for each customer | INT (Primary Key) |
| age | Customer's age in years | INT |
| job | Customer's occupation category | VARCHAR(20) |
| marital | Marital status ('single', 'married', 'divorced') | VARCHAR(10) |
| education | Highest education level completed | VARCHAR(20) |
| default | Has credit in default? ('yes', 'no') | VARCHAR(3) |
| housing | Has housing loan? ('yes', 'no') | VARCHAR(3) |
| loan | Has personal loan? ('yes', 'no') | VARCHAR(3) |
| contact | Contact communication type ('cellular', 'telephone') | VARCHAR(10) |
| month | Last contact month of year (3-letter abbreviation) | VARCHAR(3) |
| day_of_week | Last contact day of week (3-letter abbreviation) | VARCHAR(3) |

### Campaigns Table
| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| campaign_id | Identifier for marketing campaign | INT |
| customer_id | Reference to customer (Foreign Key) | INT |
| campaign_type | Marketing channel used ('email', 'telemarketing', etc.) | VARCHAR(15) |
| campaign_date | Date when campaign was executed | DATE |
| duration | Contact duration in seconds | INT |
| contacts | Number of contacts during this campaign | INT |
| pdays | Days since last contact (999 = not previously contacted) | INT |
| previous | Number of contacts before this campaign | INT |
| poutcome | Outcome of previous marketing contact | VARCHAR(12) |
| outcome | Current campaign result ('yes' = subscribed, 'no' = did not) | VARCHAR(3) |

### Financials Table
| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| customer_id | Reference to customer (Foreign Key) | INT |
| balance | Average yearly account balance in EUR | DECIMAL(10,2) |
| emp_var_rate | Employment variation rate (quarterly) | DECIMAL(3,1) |
| cons_price_idx | Consumer price index (monthly) | DECIMAL(6,3) |
| cons_conf_idx | Consumer confidence index (monthly) | DECIMAL(4,1) |
| euribor3m | 3 month Euribor interest rate | DECIMAL(3,1) |
| nr_employed | Number of employees (quarterly) | DECIMAL(6,1) |


## 🔍 Analysis Highlights

## 🔍 Key Findings

### 🎯 **Top-Performing Segments**
| Segment | Conversion Rate | Lift vs Avg |
|---------|-----------------|-------------|
| **Managers (Basic.6y education)** | 36.63% | 1.87× |
| **Retirees (Vocational training)** | 29.25% | 1.50× |
| **Seniors (Age 60+)** | 25.13% | 1.57× |

### 📊 **Campaign Effectiveness**
- **In-branch campaigns convert 2× better** (31.88%) than digital channels  
- **Telemarketing beats expectations** (18.67% vs 15.6% for email)  
- **Best months**: Feb (22.75%) & Nov (21.24%)  
- **Worst month**: Sep (16.93%)  

### 💰 **Financial Insights**
- **Negative balances (-€5k to -€3.3k) convert at 20.4%** (likely debt consolidation seekers)  
- **Wealthiest customers (€3k+ balance)**: 21.04% conversion  

### 📈 **Predictive Factors**
1. **In-branch execution** (1.90× lift)  
2. **Previous success history** (1.94× lift)  
3. **Economic sweet spot**:  
   - Employment variation: -0.54  
   - Consumer confidence: -35.04  
   → **21.23% success rate**  

### 🧩 **Surprising Discoveries**
- **Basic education > Degrees** for managers (36.6% vs 27.9%)  
- **Blue-collar workers** outperform technicians (25.5% vs 26.6%)  
- **Vocational-trained retirees** beat degree-holders (29.3% vs 27.9%)  

