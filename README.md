## Introduction
Health care is an important part of living in Nova Scotia. Traditionally people accessed the healthcare system through their Family Physician.  As of April 1, 2020, [46,051](http://www.nshealth.ca/sites/nshealth.ca/files/finding_a_primary_care_provider_in_nova_scotia_report_april_2020.pdf) Nova Scotians have indicated that they are unable to find a Family Physician.
This report will look at:
*The distribution of Family Physicians in Nova Scotia.
*If there will be shortage of Family Physicians in the future due to retirements.

## Data

### The Forward Sortation Area
This report relies heavily on data that has been segmented by geographic region.  The fundamental region utilized is the Forward Sortation Area (FSA).  The FSA is the first half of a Canadian Postal code. *ie. **B3K** 2T3*. Statistics Canada publishes some data by linking it with an FSA.  Statistics Canada also publishes a GIS file containing the [FSA boundaries](https://www150.statcan.gc.ca/n1/en/catalogue/92-179-X) of Canada.

![Nova Scotia Forward Sortation Areas](NovaScotiaFSA.jpeg)

### Population
The distribution of Nova Scotia’s population was obtained from Statistics Canada’s [Population and Dwelling Count Highlight Tables, 2016 Census]( https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/hlt-fst/pd-pl/Table.cfm?Lang=Eng&T=1201&S=22&O=A)

### Family Physician Data
The data pertaining to Physicians was obtained through the [College Of Physicians & Surgeons Of Nova Scotia](https://cpsns.ns.ca/).  This site has a link to a Physician search where the user can download a .CSV file that contains summary information on every Physician practicing in Nova Scotia.  While the file contains useful information, it is missing information regarding:
*A Physician’s age. 
*A way to associate a Physician to a FSA.  
A simple web scraper script was created in RStudio using the rvest package to retrieve this information from the College of Physicians & Surgeons Of Nova Scotia.

## ETL, Calculation and Graphics
All ETL, calculations and graphics were performed through an RStudio script written specifically for the tasks.

## Distribution of Family Physicians in Nova Scotia
Combining the number of Family Physicians with the population in each FSA it is possible to calculate number of Family Physicians per 100,000 people in each FSA.  This metric is used to apply a colour gradient to each FSA in Nova Scotia.  The map is shown below.

![Doctors Per 100K](DocsPer100K.jpeg)

In the above map there are areas that are grey coloured, these are areas where a Family Physician is not practicing.  These areas are close to the HRM, Truro and in Eastern Cape Breton.  The areas around the HRM and Truro can be explained due to their proximity to a large population center.  The lack of a Family Physician in Eastern Cape Breton is less likely due to its proximity to Sydney and may be an area that is genuinely in need of Family Physicians
The area covered by each FSA can vary significantly and when used to plot data can obscure the results.  By associating each FSA with a named region, it is possible to group the FSAs and make comparisons.

Insert Grouped FSA Bar

Surprisingly, the HRM is not the community with the highest number of Family Physicians per 100,000 people. The top four communities do have a common factor, they are all University communities.

## Estimating Family Physician Retirements
Using the year a Physician graduated from Medical School it is possible to estimate their age.  The data retrieved from the College Of Physicians & Surgeons Of Nova Scotia contains the reason and date a Physician has inactivated their licence in Nova Scotia.  Utilizing these criteria, I have calculated the average retirement age for a Family Physician as 64.3 years.
Applying the calculated retirement age to the active Family Physicians in Nova Scotia, it is possible to estimate how many of these Physicians are within five years of retirement. Grouping Family Physicians by community it is possible to predict which communities may be hit hardest by Physician retirements in the next five years.

Insert retirements Chart   

From the above chart the top three communities that could be impacted by Family Physician retirements are Enfield, Liverpool and New Glasgow.



























## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/acarmichael20/CapstoneProject/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/acarmichael20/CapstoneProject/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
