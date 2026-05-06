# imdb-eda-pandas

🎬 IMDB Movie Dataset — Exploratory Data Analysis (EDA)

A hands-on Python + Pandas project that cleans, explores, and extracts insights from an IMDB movies dataset — covering everything from data wrangling to business-level questions about genres, directors, ratings, and box office performance.


📌 Project Overview
This project performs end-to-end Exploratory Data Analysis on a real-world IMDB movies dataset using Python and Pandas. The notebook is structured as a question-driven investigation — each cell answers a specific analytical question, making it easy to follow for beginners and useful as a portfolio piece for intermediate analysts.

🗃️ Dataset
File: movies.csv
ColumnDescriptionidUnique movie identifiernameMovie titleyearRelease yeargenreOne or more genres (comma-separated)ratingIMDB rating (0–10)votesNumber of audience votesdurationRuntime (raw string, e.g. "175 min")certificateContent rating (R, PG-13, PG, etc.)gross_incomeBox office gross (raw string, e.g. "$123.4M")directors_nameDirector(s) name(s)

🧹 Data Cleaning
A significant portion of the project focuses on transforming raw, messy columns into analysis-ready types:
ColumnProblemSolutiondurationString like "175 min"Strip "min", remove commas → cast to intvotesString with commas like "1,234,567"Remove commas → cast to intgross_incomeString like "$123.4M"Strip $, M, commas → cast to floatgenreMulti-value string like "Action, Drama".str.split().explode() for per-genre analysisdirectors_nameMulti-value string.str.split().explode() for per-director analysis

🔍 Questions Answered
🏗️ Setup & Exploration
#QuestionQ1How do we load the dataset and view sample rows? (head, tail, sample)Q2What are the data types of each column? (info, describe)
🧹 Data Cleaning
#QuestionQ3How do we clean the duration column? ("175 min" → 175)Q4How do we clean the gross and votes columns?Q5How many missing values are in each column?
📊 Analysis & Insights
#QuestionQ7Find Hidden Gems — high rating, low votesQ8Find Overhyped Movies — low rating, high gross incomeQ9What unique certificates exist in the dataset?Q10How many movies were released each year?Q11What are the top 5 most common genres?Q12Which directors have directed the most movies?Q13Do longer movies get better ratings? (correlation analysis)Q14Which genre has the highest average rating?Q15Which genre makes the most money on average?Q16Who is the highest-grossing director of all time?Q17How does certificate type affect gross income?Q19Are IMDB ratings improving over the years?

💡 Key Findings

Hidden Gems are identified as films with rating > 6.9 but fewer than 1,058 votes — critically appreciated but under-seen.
Overhyped films have ratings below 5.3 yet crossed $12.4M in gross — commercially successful but poorly reviewed.
Genre analysis requires exploding multi-value genre strings before grouping, revealing true per-genre distributions.
Duration vs. Rating and Votes vs. Gross Income correlations are computed to test common assumptions about movie quality and commercial success.
Content certificate has a measurable effect on average gross income — certain ratings consistently outperform others at the box office.


🛠️ Tech Stack
ToolPurposePython 3.xCore languagePandasData manipulation and analysisGoogle Colab / JupyterNotebook environment

🚀 Getting Started
1. Clone the repository
bashgit clone https://github.com/your-username/imdb-eda-pandas.git
cd imdb-eda-pandas
2. Install dependencies
bashpip install pandas
3. Run the notebook
Open project_imdb_dataset_v2.ipynb in Jupyter Notebook or upload it directly to Google Colab.
Make sure movies.csv is in the same directory (or update the file path inside the notebook).

📁 File Structure
imdb-eda-pandas/
│
├── project_imdb_dataset_v2.ipynb   # Main analysis notebook
├── movies.csv                      # Dataset (add manually)
└── README.md                       # Project documentation

🛠️ Skills Demonstrated

Data Loading & Inspection — head(), tail(), info(), describe(), sample()
Data Cleaning — String stripping, type casting, handling missing values
Multi-value Column Handling — .str.split() + .explode() for genre and director columns
GroupBy Aggregations — groupby() with mean(), sum(), count()
Sorting & Filtering — Boolean indexing, sort_values()
Correlation Analysis — .corr() between numerical columns
Descriptive Statistics — isnull(), nunique(), value_counts()


👤 Author
[Your Name]
Aspiring Data Analyst | Python & SQL Enthusiast
LinkedIn · GitHub · Portfolio

📄 License
This project is open-source and available under the MIT License.
