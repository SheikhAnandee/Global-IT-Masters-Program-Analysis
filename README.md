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
<p align="center"> <img src="visualizations/tuition-dashboard.png-1" width="900"> </p>
Visualizations: <br/>
1) Tuition Fee Heatmap across countries and rating categories (excluding Singapore)
2) Bar Chart of Average Tuition Fee by Country
3) Scatter Plot of Average Tuition Fee vs. Average Rating, analyzing whether higher tuition fees are associated with better program ratings worldwide
4) Scatter Plot: Average Monthly Tuition vs. Program Duration (USA)

### Dashboard 2: Ranking & Geographic Distribution
<p align="center"> <img src="visualizations/ranking-dashboard-2.png" width="900"> </p>
Visualizations: <br/>
1) List of Top-Ranked Universities Offering Data Science Master’s Programs Worldwide
2) Map of European Countries Showing Universities Offering AI, Cybersecurity, and Data Analytics Programs.
3) Bar Chart of Number of Top-Ranked Universities in affordable countries.
4) Bubble Chart comparing average tuition fees and ratings across countries, with bubble size reflecting top-ranked universities and review volume.
5) Dual-Axis Line Chart: Relationship Between Program Ranking, Average Rating, and Review Count

You can visit the public [Dashboard](https://public.tableau.com/views/GlobalITMastersProgramsAnanlysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) 
## Interesting findings from both dashboards
1) Universities with Excellent ratings (≥4.5) are slightly cheaper than those with Very Good ratings (≥4).
2) Program ratings remain consistently strong across all tuition ranges, indicating that higher cost does not necessarily guarantee better quality.
3) Most programs in the USA are 12 months long.
4) Some 24-month programs are cheaper than certain 8-, 10-, or 12-month programs, which is unusual.
5) USA has the highest average tuition fee, while Italy has the lowest average tuition fee
6) Programs with similar ratings (≈4.0–4.5) appear across a wide tuition range
7) Europe offers the best balance of affordability, high-quality education, and strong global rankings.
8) Program duration varies widely: Europe leans toward 2-year programs, while the USA and UK generally offer 1-year programs.
9) The UK stands out as one of Europe’s largest contributors, offering hundreds of programs in Cybersecurity, AI, and Data Analytics across a wide range of universities.
10) Average program ratings remain consistently high across rankings, indicating stable quality, while review counts vary significantly, suggesting that higher rankings are more closely linked to quality than to popularity.
    
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
   
## Analytics   
View the dashboards:

[Dashboard](https://public.tableau.com/views/GlobalITMastersProgramsAnanlysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## Feedback & Contact
If you have suggestions, questions, or ideas to improve the dataset or dashboard, feel free to reach out. Feedback and discussions are always welcome.
<br/>
Email: anandeehasan24@gmail.com
