# Scholar_Scraper

Please see the ss_workflow.pdf file for detailed setup instructions with screenshots. 


## Introduction


This project automates the process of scraping this information from Google Scholar for a list of authors. It utilizes scholarly, a Python module that allows users to retrieve bibliometrics from Google Scholar.

The project includes the following files:

ScholarScraper.ipynb - the main notebook (Python) which takes an author list CSV as input and outputs a CSV with author data. It also outputs a bar chart of the total citations per year for the entire list of authors.

ScholarCollabs.ipynb - this is an R notebook that takes the author data CSV outputted by ScholarScraper.ipynb and creates a chord diagram to visualize publication collaborations between authors. It outputs the chord diagram as a PDF.

GroupedCollabs.ipynb - this is an R notebook that performs similarly to ScholarCollabs, but also groups the authors in subgroups (e.g. faculty, research area, etc). It takes an additional CSV with the subgroups as input.

DBC Investigators.csv - this is an example author list CSV. 

DBC-Investigator-Faculty-Groups.csv - this is an example subgroups CSV. 

This project currently works with scholarly 1.4.5

## Installation and Setup

1. Set-up Jupyter. If your institution has access, you can use [Syzygy](https://syzygy.ca/) to run in the Cloud, or install on your computer following [these instructions](https://jupyter.org/install).
2. Clone the project.
    - Open Terminal (in Syzygy, click the "+" button to open a new launcher and click "Terminal"
    - Type  "git clone https://github.com/ubcbraincircuits/ScholarScraper" and press enter
    - The project should now be cloned in your directory. 
    - Alternatively, you can download the project as a ZIP file from https://github.com/ubcbraincircuits/ScholarScraper (click Code, then Download ZIP)
3. [Install scholarly](https://pypi.org/project/scholarly/)
    - In the terminal (from above) type "pip install scholarly" and press enter
4. Obtain a CSV file with the list of author names in a single column with no column header. Ideally, all author names should match their names in Google Scholar. Upload this file to Syzygy or move it to the project folder on your computer. This file should be in the same directory as ScholarScraper.ipynb. 

### ScholarScraper
5. Open ScholarScraper.ipynb. Modify the names of the input/output files below (in step 1). The input file name must match the CSV file name. 
6. Modify the "affiliations" variable as a list of institution names which the researchers are affiliated with. Include both abbreviated and long form.  
7. Run all cells. 
8. Open the ouput CSV file in the main project directory. Check the last column of this file for warnings. If needed, modify the author names in the input CSV file if the wrong author profile was scraped, or no profile was found, and re-run.

### ScholarCollabs
9. Modify the ss_output_file and the author_name_file strings to match the names of your files.
10. Modify the title of the diagram.
11. Modify "links" depending on whether you want a weighted or non-weighted diagram.
12. Modify the name of the output PDF file.
13. Run all cells, and find the diagram outputted to the main directory as a PDF. 


### GroupedCollabs
14. Create a CSV file for the groupings. This should contain the author names in the first column, the group names as column names, and the author names under their respective groups. See DBC-Investigator-Faculty-Groups.csv for an example. Upload this file to the main project directory. Modify the group_file string to match this file name.
15. Follow the same steps as above (for ScholarCollabs). 


