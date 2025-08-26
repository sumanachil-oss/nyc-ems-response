# EMS Response Times in NYC (2021)

**Authors**: Sumana Chilakamarri & Diya Mohan  

---

##  Project Overview
This project investigates how **a neighborhood’s economic wealth affects access to emergency medical services (EMS)** in **New York City** across its five boroughs: Manhattan, Queens, the Bronx, Brooklyn, and Staten Island.  

We hypothesized that **lower-income boroughs face more barriers to efficient EMS response times** compared to higher-income boroughs. Using datasets from 2021, we analyzed demographic patterns, EMS response times, and disparities across boroughs.  

---

##  Data Sources
We used three key data sources:
- **Borough Demographics API** → Median household income & poverty rates
- **NYC EMS Case Dataset** (~24M rows) → Incident-level response data (2005–2022)
- **Monthly EMS Response Times (JSON)** → Average monthly response times by borough

---

##  Methodology

### **1. Data Cleaning**
- **EMS Dataset (24M rows, 5.2GB)**: Split into chunks, filtered for **2021**, dropped invalid values, handled outliers.
- **Borough Demographics API**: Web scraped using `BeautifulSoup` to extract **median income** & **poverty rates**.
- **Monthly Response Times JSON**: Extracted borough-level response times, aggregated monthly.

### **2. Data Analysis**
- Predicted **2021 borough demographics** using **linear regression**.
- Grouped EMS cases by borough, analyzed **treated vs. untreated** cases.
- Measured disparities in **incident vs. dispatch response times**.
- Compared **mean, median, and variance** of EMS times across boroughs.

### **3. Data Visualizations**
- Borough-level comparisons of **treated vs. untreated EMS cases**
- Scatter plots of **incident vs. dispatch response times**
- Residual plots to evaluate regression fits
- Boxplots of borough-level response time distributions

---

##  Key Findings
| Insight | Summary |
|--------|---------|
| **Disparity Exists** | Lower-income boroughs (e.g., Bronx, Brooklyn) had **lower EMS treatment rates** than higher-income ones. |
| **Queens vs. Manhattan** | Queens, despite being middle-income, had the **highest treatment percentage**. |
| **Residual Analysis** | Bronx showed more cases where **actual response time < predicted**, contradicting parts of our initial hypothesis. |
| **Response Times** | Bronx & Brooklyn had the **highest mean & median EMS response times**; Manhattan had the lowest. |

---

##  Repository Structure
```bash
nyc-ems-response/
│── EMS_Response_Times.ipynb     # Jupyter Notebook with analysis
│── EMS_Presentation.pptx        # Project presentation slides
│── requirements.txt             # Python dependencies
│── README.md                    # Project overview & methodology
```

---

##  Getting Started

### **1. Clone the Repository**
```bash
git clone https://github.com/<your-username>/nyc-ems-response.git
cd nyc-ems-response
```

### **2. Create a Virtual Environment**
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
```

### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

### **4. Run the Notebook**
```bash
jupyter notebook EMS_Response_Times.ipynb
```

---

##  Project Presentation
📑 **[Download the Presentation](./EMS_Presentation.pptx)**  


---

## Project Highlights
- 24M-row dataset analyzed  
- Web scraping + regression modeling  
- Data storytelling with visualizations  
