# Global Analysis of IT Master's Programs
## Quick Links
- **Live Dashboard:** [View on Tableau Public](https://public.tableau.com/views/GlobalITMastersProgramsAnanlysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- **Dataset (CSV):** [View Dataset](data/CS_master_program_details_top35_countries.csv)
- **Scraper Code:** [View Scraper](src/scraper.py)
- **Data Source:** [Mastersportal website](https://www.mastersportal.com/)
- **Full Repository:** [GitHub Repo](https://github.com/SheikhAnandee/Global-IT-Masters-Program-Analysis.git)
- **Contact:** anandeehasan24@gmail.com
## Objective
Build a centralized dataset and interactive dashboard to compare global Computer Science & IT Master’s programs across 35+ countries.
## Project Background
Comparing Computer Science and IT master’s programs across countries is challenging due to fragmented and inconsistent information spread across multiple university websites. This project addresses that problem by automating the collection of standardized program data from 35+ countries.
Using Selenium with Undetected-Chromedriver, the project scrapes on-campus CS & IT master’s program information from the [MastersPortal](https://www.mastersportal.com/) website.The resulting dataset is structured, consistent, and ready for analysis, enabling efficient cross-country comparisons of tuition, rankings, duration, and availability.
## Data Scraping & Preprocessing
### Data Collection
Program data is automatically scraped from paginated search results on [MastersPortal](https://www.mastersportal.com/)  using Selenium and Undetected-Chromedriver to bypass anti-bot protections. 
Key attributes collected include:
- Program Name
- University
- City
- Country
- Tuition Fee
- Duration
- Average Rating
- Review Count
- Global Ranking Percentage
- Program Links

### Data Cleaning
- Parsed location strings into separate city & country
- Cleaned review counts (removed extra characters)
- Handled missing values safely
- Converted tuition fields to numeric format
- Exported clean, analysis-ready dataset using Pandas

The final output is stored as a clean, analysis-ready [CSV file](data/CS_master_program_details_top35_countries.csv) using Pandas.

## Data Analysis & Visualization
### Dashboard 1: Tuition Analysis
<p align="center"> <img src="visualizations/tuition-dashboard-1.png" width="900"> </p>

### Visualizations: 
1. **Tuition Fee Heatmap**
   - Compares tuition fees across countries and rating categories (excluding Singapore).

2. **Bar Chart: Average Tuition Fee by Country**
   - Highlights countries with the highest and lowest average tuition costs.

3. **Scatter Plot: Average Tuition Fee vs. Average Rating**
   - Analyzes whether higher tuition fees are associated with better program ratings worldwide.
   
4. **Scatter Plot: Average Monthly Tuition vs. Program Duration**
   - Examines cost efficiency patterns across different program lengths.
   - The country can be dynamically selected using the dashboard filter.

### Dashboard 2: Ranking & Geographic Distribution
<p align="center"> <img src="visualizations/ranking-dashboard-2.png" width="900"> </p>

### Visualizations: 

1. **List of Top-Ranked Universities Offering Data Science Master’s Programs Worldwide**

2. **Map of European Countries Showing Universities Offering AI, Cybersecurity, and Data Analytics Programs**

3. **Bar Chart: Number of Top-Ranked Universities in Affordable Countries**

4. **Bubble Chart: Average Tuition vs Rating Comparison**
   - Bubble size reflects number of top-ranked universities and review volume

5. **Dual-Axis Line Chart: Relationship Between Program Ranking, Average Rating, and Review Count**

You can visit the public [Dashboard](https://public.tableau.com/views/GlobalITMastersProgramsAnanlysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) 

## Interesting Findings from Both Dashboards

- **Excellent-rated programs (≥4.5)** are slightly cheaper than those with “Very Good” ratings (≥4.0).  
- **Program ratings** remain consistently strong across all tuition ranges, showing that higher cost does not guarantee better quality.  
- Most programs in the **USA** have a **12-month duration**.  
- Some **24-month programs** are cheaper than certain 8–12 month programs, which is unusual.  
- The **USA** has the highest average tuition fee, while **Italy** has the lowest.  
- Programs with similar ratings (≈4.0–4.5) span a **wide tuition range**.  
- **Europe** offers the best balance of **affordability, quality, and global rankings**.  
- Program duration varies widely: Europe favors **2-year programs**, while the USA and UK mostly offer **1-year programs**.  
- The **UK** is one of Europe’s largest contributors, offering hundreds of programs in **Cybersecurity, AI, and Data Analytics**.  
- **Average program ratings** are consistently high across rankings, while **review counts** vary, indicating that **ranking correlates more with quality than popularity**.
    
## Build from sources and run the selenium scrapper
1) Clone the repository
 ```bash

   git clone:https://github.com/SheikhAnandee/Global-IT-Masters-Program-Analysis.git

  ```
2) Initialize and activate virtual environment <br/> 
For Windows:
 ```bash
    python -m venv venv
    venv\Scripts\activate
 ```
For Linux / macOS:
 ```bash

   python3 -m venv venv
   source venv/bin/activate

 ```
3) Install dependencies
 ```bash

    pip install -r requirements.txt

 ```
4) Download the correct version of Chrome WebDriver that matches your browser version:https://developer.chrome.com/docs/chromedriver/downloads

5) Run the scrapper
 ```bash

  python python src/scraper.py--chromedriver_path <path_to_chromedriver>

 ```
 
6) After running, you will get a file named "CS_master_program_details_Top35_Countries.csv" containing all the required details
   Alternatively:
   Check our scraped data here: https://github.com/SheikhAnandee/Global-IT-Masters-Program-Analysis/tree/main/data/CS_master_program_details_top35_countries.csv
   
##  Analytics & Interactive Dashboard

Explore the full interactive Tableau dashboard to analyze tuition trends, rankings, program distribution, and cross-country comparisons in detail.

 **Live Dashboard:**  
 [View on Tableau Public](https://public.tableau.com/views/GlobalITMastersProgramsAnanlysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


## License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute this project with proper attribution.

## Acknowledgments

- **MastersPortal** – For providing structured access to global master’s program information.
- **Tableau Public** – For enabling interactive data visualization and dashboard publishing.
- **Selenium & Undetected-Chromedriver Community** – For automation tools used in large-scale data scraping.
- **Open Source Community** – For the Python libraries and ecosystem that made this project possible.

## Feedback & Contact
If you have suggestions, questions, or ideas to improve the dataset or dashboard, feel free to reach out. Feedback and discussions are always welcome.
<br/>
Email: anandeehasan24@gmail.com
