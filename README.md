# Firm-Vertical-Relatedness-Measure
Estimate a firm's vertical relatedness based on the Industry Input-Output Table and its segments' sales

## Installations

The code should run with no issues using Jupyter Notebook with kernel `Python 3.x`

## Project Motivation

For this project, I was interested to measure firms' vertical relatedness by following the method in  **Fan, J. P. H. & Lang, L. H. P. The Measurement of Relatedness: An Application to Corporate Diversification. *J Bus* 73, 629–660 (2000).**  

With the estimated data, I can better understand firms' vertical relatedness changes from 1992 to 2019.

## Project Methods

### Steps to measure firms' vertical relatedness 

- Measuring interindustry vertical relatedness
  1. <img src="https://render.githubusercontent.com/render/math?math=a_{ij}">: each pair of industry, *i* and *j*, the dollar value of *i*’s output required to produce industry *j*’s total output
  2. <img src="https://render.githubusercontent.com/render/math?math=v_{ij}">: <img src="https://render.githubusercontent.com/render/math?math=a_{ij}\/ \text{the dollar value of industry j’s total ouput}">
  3. <img src="https://render.githubusercontent.com/render/math?math={V_{ij}=1/2(v_{ij} %2B v_{ji})}">: a proxy for the opportunity for vertical integration between industries *i* and *j* .
- Measuring firms' vertical relatedness
  1. <img src="https://render.githubusercontent.com/render/math?math=w_j">: the weight of segment sales in all segment sales except the primary segment *i* with the highest segment sale
  2. <img src="https://render.githubusercontent.com/render/math?math=V = \sum_{j}(w_{j}\times V_{ij})">: a firm's vertical relatedness is the weighted average interindustry vertical relatedness by segments sale

### Steps to process data

1. Read `IO table` from Year 1992, 1997, 2002, 2007, 2012
2. Create IO coeffcient table
3. Create industry vertical relatedness table
4. Create NAICS(SIC)-IO conversion table
5. Build NAICS(SIC)-IO vertical relatedness function
6. Read Sales table
7. Calculate firm vertical relatedness based on sales

## File Descriptions

All input-Output Data can be download from: https://www.bea.gov/industry/benchmark-input-output-data#1992data

- IO table is in the folder: `IO*`
- NAICS(SIC) to IO industry codes conversion tables are manually created in `IO*` folder
- Firms' segment sales data can be accessed from [WRDS - Compustat - Historical Segments section](https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/historical-segments-daily/historical-segments/). 

The notebook here shows the process for constructing the dataset for all firms in the WRDS Compustat Database from 1992 to 2019. 

## Result

The main findings of the code can be found at the post available here. 

## Reference

Reference:

1. Fan, J. P. H. & Lang, L. H. P. The Measurement of Relatedness: An Application to Corporate Diversification. J Bus 73, 629–660 (2000).
2. Compustat Segments - S&P Global Market Intelligence Data Through Wharton Research Data Services
3. The U.S. Bureau of Economic Analysis -Input-Output Accounts Data
