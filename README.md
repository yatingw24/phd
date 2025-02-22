# PhD Candidates in Humanities and Arts are Struggling Financially 
Trump's recent decision to slash funding to research institutions and health systems has sent shockwaves through academia. In response, many universities have been forced to halt new admissions, leaving students and faculty grappling with the fallout. However, the financial struggles for Humanities, Arts, and Social Science phD students date back much earlier, **long before this funding cut**. 

Here is the shortcut to my [article:](https://yatingw24.github.io/phd/)

A great thank to my data sources:
- [PhD Stipends](https://www.phdstipends.com/) for sharing the financial information about PhD students in many disciplines at universities across the US in different academic years.
- [A statistical Report on English PhD Stipends in the US](https://profession.mla.org/english-phd-stipends-in-the-united-states-statistical-report/) for collecting data on stipends for PhD candidates in English conducted between summer 2021 and spring 2022.


## Key Takeaways 
Except for Business PhDs, stipends in other disciplines fall below the 2024 U.S. median cost of living ($3,851/month) and are quickly drained by basic expenses;

Students in Humanities, Arts and Social Sciences can hardly earn a stipend that would catch up with candidates in STEM and Business majors for almost a decade;

A PhD student's stipend is not necessarily tied to their year in the program;

## Questions That This Article Would Answer:
1. What are the reason(s) students in non-STEM disciplines receive fewer stipend? Has this been a trend for a long time before union strikes and even before Covid?
2. What does a Humanity PhD candidate's budget looks like after the deduction of living cost? 
3. Is there a decrease/increase in doctoral enrollments in disciplines such as Humanities, Arts and Social Science in recent years?
4. Are PhD students more or less financially struggling depending on which discipline he chooses?

## What I Did:
### Tech Stack sed:
 - `python - pandas`
 - `R`
 - `regex`
 - `csv`

### A Break Down of Files:
 - `Analysis.ipynb`: the jupyter notebook where I did my majority of data cleaning and analysis.
  - `ggplot_dist.ipynb`: the jupyter notebook where I used R console to generate charts and plots. 
 - `cleaned_output.csv`: the curated dataset after my categorization of majors into four disciplines - Business, Science, Social Science and Humanities. 
 - `debt.csv`: a breakdown of percentage of debt by discipline.
  - `treemap.csv`: a spreadsheet which eventually presented through a treemap that shows the total number of doctoral enrollments in 2024 by discipline. 
 - `phd_stipends.csv`: the original dataset that contains all financial information about nationalwide stipends across discipines. 
 - static_imgs: charts and graphics you find in my article.
  - `privater.csv` and `public.csv`: data about English PhD stipends in public universities and private universities. 

### Data Cleaning and Analysis 
1. Opened `phd_stipends.csv` and dropped all irrelevant, confusing and null entries including NA and Non-English characters 
2. Create a new column that categorizes majors into four primary disciplines: Business, Hard-core Science, Social Science and Humanities and Arts. For Humanities, here is a sample code:
```python
    df.loc[df["Department"].str.contains("A|B|C|...", case=False, na=True), "Field"] = "Humanities"
```
3. separated first names and last names and converted each name into the standard name format.
4. replaced all signs, such as a dollar sign ($) or a percentage sign (%).
5. selected columns, `member`, `90s_Appearance_Percent` and `80s_Appearance_Percent` to see the change in the amount of presence in issues published in the 80s versus the 90s:

- `member`: X-Men's names.
- `90s_Appearance_Percent`: the percentage of appearance in issues published after 1990.
- `80s_Appearance_Percent`: the percentage of appearance in issues published between 1980 and 1989.

6. analyzed the market value of each X-Man by pulling out columns `PPI80s_ebay` and `PPI90s_ebay`:

- `PPI80s_ebay`: average market price for a certain X-Man on eBay for issues on Very Good Condition published between 1980 and 1989;
- `PPI90s_ebay`: average market price for a certain X-Man on eBay for issues on _Very Good Condition_ published after 1990;

7. exported dataframes into csv ready for upload in Data viz tool.

### Data Vizs 
1. represent the change in percentage of presence from the 80s to the 90s with a side-by-side <ins>horizontal stack bar chart:
- those with an increase of presence were highlighted.

2. show female X-Men's average price over time in two separate scatterplot.
- x-axis: Average price per issue published in the 80s and the 90s. 
- y-axis: Percentage of Appearance for each X-Men character in issues published in the 80s and the 90s. 
- each green circle represents one female X-Man. 

### Skills Newly Acquired
1. used both pandas and regex to curate a clean dataframe;
2. practiced html and css when building the story page for this project;
3. converted data analysis and findings into journalistic languages.

## Limitations & Things I'd Like to Improve
1. This is a data-driven project done with a limited amount of time - 
2. The dataset also listed average prices on various auction sites such as heritage. A comparison between price difference for each character on different sites could be also interesting. 
3. While more and more female superheros emerge, how their value in second-hand market is different from male X-Men's is worth analyzing. 
 
