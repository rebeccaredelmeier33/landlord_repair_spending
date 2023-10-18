**Analysis of NYC landlord expenses and maintenance spending – Tax Commission TC201 Form — 2021**

This repository contains data and analytic code that support the CUNY j-school analysis of landlord spending on rent stabilized units. This analysis was done by Liz Rosenberg, Yi Liu, and Rebecca Redelmeier for Lam Thuy Vo's advanced data journalism class.

**Data**

This analysis uses the rent-data.csv and buildings\_list.csv spreadsheets.

The spreadsheets come from the following sources:

- New York City Tax Commission

  - ‘rent-data.csv': This includes raw data from forms landlords file with the city's Tax Commission when applying to dispute their tax bills. Not every landlord files this form every year, but many do to request lower tax rates.

<!---->

- Just Fix (nonprofit group)

  - ‘buildings\_list.csv’: This is a list of buildings owned by the two landlords, Maxwell Rovt and Robert Iszak, we are investigating, including their BBL indicators, compiled by other teammates.

The rent-data.csv contains among others, the following columns:

- TOTAL EXPENSES — Total expenses landlords spent on the buildings, self-reported to tax commission
- TOTAL INCOME FROM REAL ESTATE — Total income landlords receive from the building, elf-reported to tax commission
- REPAIRS AND MAINT. - Total landlords spend specifically on repairs and maintenance of the building, self-reported to tax commission
- Methodology

The  buildings\_list.csv contains, among others, the following columns:

- BBL – the borough, block, and lot number for each building, which is a unique identifier

**Analysis**

The notebook analysis.ipynb performs the following analyses:

**Part 1: Finds expense cost as percent of income, repairs and maintenance cost as percent of income, and repairs and maintenance as percent of total expenses** 

Looks at how much landlords have been spending on expenses, and specifically on repairs, including: 

- Calculates percentage of total expense cost spent on expenses
- Calculates percentage of total expense cost spent on repairs
- Calculates percentage of expenses spent on repairs

This section also uses a describe() function to look at the min, max, mean, and median of spending on repairs as percent of income in this data.

**Part 2: Filters data to remove buildings with very low income**

This filters out buildings where landlords’ income is less than $500,000, to get rid of landlords that have reported $0 or other minimal amounts of rental income. 

This also filters out buildings with NULL values for expenses.

This section also uses a describe() function to look at the min, max, mean, and median of spending on repairs as percent of income in this data after it has been filtered.

This section outputs the expense and repair spending as percentage of income for the filtered building list into the file ‘tax\_data\_BuildingAnalysis.csv'

**Part 3: Looks specifically at the landlords’ buildings and expense and repairs spending as percent of income for only those buildings** 

By merging the rent\_data with the list of buildings owned by the specific landlords we are investigating, we found how much those landlords have been spending on expenses and repairs.

This section also uses a describe() function to look at the min, max, mean, and median of the landlords’ spending on repairs as percent of income.

This section outputs the landlords’ expense and repair spending as percentage of income in the file ‘relevant\_buildings\_expenses.csv’

**Outputs**

‘output/tax\_data\_analysis.csv’: This includes total expenses percent of income and total repairs as percent of maintenance for all buildings where income is more than $500,000 and whose expense values are not NULL

‘output/relevant\_buildings\_expenses.csv’: This includes total expenses percent of income and total repairs as percent of maintenance for all buildings owned by Rovt and Iszak, the specific landlords we are investigating.

**Running the analysis yourself**

You can run the analysis yourself. To do so, you'll need the following installed on your computer:

Python 3

Pandas

**A final note: Our Data’s Connections With City Data**

The [Rent Guidelines Board did a study](https://rentguidelinesboard.cityofnewyork.us/wp-content/uploads/2023/03/2023-IE-Study.pdf) to examine landlords’ costs as compared to their income. One data point relevant to the two landlords we are investigating shows that on average landlords spend 17.6 percent on maintenance. The buildings we focussed on, owned by Rovt and Iszak, spent on average 11.1 percent on repairs and expenses, and in one building they spent as little as 2.5 percent. Complimentary to this data are another group’s findings that these buildings have an inordinate amount of HPD violations, something one would expect when not enough money is being spent to maintain and repair buildings. 
