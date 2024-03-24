## 💼 Project: Carbon Emission Analysis
# 1.Introduction
This report aims to analyze carbon emissions to examine the carbon footprint across various industries. We aim to identify sectors with the highest levels of emissions by analyzing them across countries and years, as well as to uncover trends.

Carbon emissions play a crucial role in the environment, accounting for over 75% of global emissions and posing a significant environmental challenge. These emissions contribute to the accumulation of greenhouse gases in the atmosphere, leading to climate change, planetary warming, and involvement in various environmental disasters.

Through this analysis, we hope to gain an understanding of the environmental impact of different industries and contribute to making informed decisions in sustainable development.

### Data Source: Where Our Data Comes From
Our dataset is compiled from publicly available data from nature.com and encompasses the product carbon footprints (PCF) for various companies. PCFs represent the greenhouse gas emissions associated with specific products, quantified in CO2 (carbon dioxide equivalent).

### Data Structure
The dataset consists of 4 tables containing information regarding carbon emissions generated during the production of goods.
![](data:image/png;base64,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)
### Tables' columns description

***

#### **1. Table 'product_emissions'**
**id:** Identifier for each product emission record.

**company_id:** Identifier for the company associated with the product.

**country_id:** Identifier for the country where the product is being produced.

**industry_group_id:** Identifier for the industry group to which the product belongs.

**year:** The year in which the emissions data was recorded.

**product_name:** The name of the product associated with the emissions data.

**weight_kg:** The weight of the product in kilograms.

**carbon_footprint_pcf:** The carbon footprint of the product, measured in CO2 equivalent.

**upstream_percent_total_pcf:** The percentage of the total carbon footprint attributed to upstream activities.

**operations_percent_total_pcf:** The percentage of the total carbon footprint attributed to operations.

**downstream_percent_total_pcf:** The percentage of the total carbon footprint attributed to downstream activities.

 
***

#### **2. Table 'industry_groups'**
**id:** Unique identifier for each industry group.

**industry_group:** The name of the industry group, categorizing businesses within similar sectors based on their products or services offered.
 

***

#### **3. Table 'companies'**
**id:** Unique identifier for each company.

**company_name:** The name of the company, identifying the specific organization within the dataset.
 

#### **4. Table 'countries'**
**id:** Unique identifier for each country.

**country_name:** The name of the country.

# 2. Project Brief
You are required to analyze the data to answer the given questions and compile a comprehensive report in the repository on Github, which includes the following:

[❗mandatory] The project report should begin with a description of the task and an overview of the tables (SQL query to each table for selecting all columns for the first 5-10 rows).
[❗mandatory] Logical division using headers of different levels.
[❗mandatory] Listings of SQL queries.
[❗mandatory] Tables with the results of SQL queries.
[❗mandatory] Text explanations for the executed queries.
[❗mandatory] Conclusions and insights based on the obtained database responses
(where you can identify potentially useful insights, interesting facts, or patterns; for example, upon closer examination, it can be observed that the "Pharmaceuticals, Biotechnology & Life Sciences" industry is one of the leaders in carbon emissions - "Now we know what our health comes at.").*

[⭐️optional] Illustrations such as photographs (e.g., cover photo at the beginning of the report), graphs (e.g., graphs generated using MS Excel or Google Sheets based on data), diagrams (database schema), and others.
[⭐️optional] Any additional research and conclusions are welcome.

# 3. Questions to research
1. Which products contribute the most to carbon emissions?
2. What are the industry groups of these products?
3. What are the industries with the highest contribution to carbon emissions?
4. What are the companies with the highest contribution to carbon emissions?
5. What are the countries with the highest contribution to carbon emissions?
6. What is the trend of carbon footprints (PCFs) over the years?
7. Which industry groups has demonstrated the most notable decrease in carbon footprints (PCFs) over time?

🚩 In addition to answering these questions, please list all insights, interesting facts, and patterns discovered in the data, such as:

1. The products with the highest levels of carbon emissions are typically associated with heavy industry.
2. The following car models are leading in carbon emissions during production: Land Cruiser Prado, Mercedes-Benz GLA, Mercedes-Benz S-Class, and Mercedes-Benz SL
3. One of the leading industries (7th place) is "Pharmaceuticals, Biotechnology & Life Sciences". Now we know what our health comes at.
   
💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💼💡💡💼💡💼💡💼💡💼

## 1. Basic Data Exploration:
#### 1.1. Table 'product_emissions'

```
SELECT * 
FROM product_emissions 
LIMIT 10;
```

| id            | company_id | country_id | industry_group_id | year | product_name                                                    | weight_kg | carbon_footprint_pcf | upstream_percent_total_pcf                       | operations_percent_total_pcf                     | downstream_percent_total_pcf                     | 
| ------------: | ---------: | ---------: | ----------------: | ---: | --------------------------------------------------------------: | --------: | -------------------: | -----------------------------------------------: | -----------------------------------------------: | -----------------------------------------------: | 
| 10056-1-2014  | 82         | 28         | 2                 | 2014 | Frosted Flakes(R) Cereal                                        | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10056-1-2015  | 82         | 28         | 15                | 2015 | "Frosted Flakes, 23 oz, produced in Lancaster, PA (one carton)" | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10222-1-2013  | 83         | 28         | 8                 | 2013 | Office Chair                                                    | 20.68     | 73                   | 80.63                                            | 17.36                                            | 2.01                                             | 
| 10261-1-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1488                 | 30.65                                            | 5.51                                             | 63.84                                            | 
| 10261-2-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1818                 | 25.08                                            | 4.51                                             | 70.41                                            | 
| 10261-3-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 2274                 | 20.05                                            | 3.61                                             | 76.34                                            | 
| 10324-1-2016  | 15         | 16         | 19                | 2016 | KURALON  fiber                                                  | 1500      | 10000                | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10418-1-2013  | 84         | 9          | 19                | 2013 | Portland Cement                                                 | 1000      | 1102                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2014 | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2015 | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) |         

#### 1.2. Table 'industry_groups'
```
SELECT * 
FROM industry_groups 
LIMIT 10;
```

| id | industry_group                                                         | 
| -: | ---------------------------------------------------------------------: | 
| 1  | "Consumer Durables, Household and Personal Products"                   | 
| 2  | "Food, Beverage & Tobacco"                                             | 
| 3  | "Forest and Paper Products - Forestry, Timber, Pulp and Paper, Rubber" | 
| 4  | "Mining - Iron, Aluminum, Other Metals"                                | 
| 5  | "Pharmaceuticals, Biotechnology & Life Sciences"                       | 
| 6  | "Textiles, Apparel, Footwear and Luxury Goods"                         | 
| 7  | Automobiles & Components                                               | 
| 8  | Capital Goods                                                          | 
| 9  | Chemicals                                                              | 
| 10 | Commercial & Professional Services                                     |         

#### 1.3 Table 'companies'
```
SELECT * 
FROM companies 
LIMIT 10;
```

| id | company_name                                   | 
| -: | ---------------------------------------------: | 
| 1  | "Autodesk, Inc."                               | 
| 2  | "Casio Computer Co., Ltd."                     | 
| 3  | "Cisco Systems, Inc."                          | 
| 4  | "CNX Coal Resources, LP"                       | 
| 5  | "Coca-Cola Enterprises, Inc."                  | 
| 6  | "Compañía Española de Petróleos, S.A.U. CEPSA" | 
| 7  | "Daikin Industries, Ltd."                      | 
| 8  | "Elitegroup computer systems co., Ltd."        | 
| 9  | "Fuji Xerox Co., Ltd."                         | 
| 10 | "Gamesa Corporación Tecnológica, S.A."         |         

#### 1.4. Table 'countries'
```
SELECT * 
FROM countries 
LIMIT 10;
```

| id | country_name | 
| -: | -----------: | 
| 1  | Australia    | 
| 2  | Belgium      | 
| 3  | Brazil       | 
| 4  | Canada       | 
| 5  | Chile        | 
| 6  | China        | 
| 7  | Colombia     | 
| 8  | Finland      | 
| 9  | France       | 
| 10 | Germany      |  

## 2. Summary of Data Analysis:
#### 2.1. Top 5 average carbon footprint per year:
```
SELECT 
    year, 
    AVG(carbon_footprint_pcf) AS avg_carbon_footprint
FROM product_emissions
GROUP BY year
ORDER BY avg_carbon_footprint DESC
LIMIT 5;
```

| year | avg_carbon_footprint | 
| ---: | -------------------: | 
| 2015 | 43188.9044           | 
| 2016 | 6891.5210            | 
| 2017 | 4050.8452            | 
| 2014 | 2457.5827            | 
| 2013 | 2399.3190            |         


#### 2.2.  Top 5 countries with total carbon footprint 
```
SELECT 
    co.country_name, 
    SUM(pe.carbon_footprint_pcf) AS total_carbon_footprint
FROM product_emissions pe
JOIN countries co ON pe.country_id = co.id
GROUP BY co.country_name
ORDER BY total_carbon_footprint DESC
LIMIT 5;
```

| country_name | total_carbon_footprint | 
| -----------: | ---------------------: | 
| Spain        | 9786130                | 
| Germany      | 2251225                | 
| Japan        | 653237                 | 
| USA          | 518381                 | 
| South Korea  | 186965                 |         

#### 2.3. Top 5 industries with the highest average carbon footprint per product
```
SELECT 
    ig.industry_group, 
    AVG(pe.carbon_footprint_pcf) AS avg_carbon_footprint_per_product
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
GROUP BY ig.industry_group
ORDER BY avg_carbon_footprint_per_product DESC
LIMIT 5;
```

| industry_group                                   | avg_carbon_footprint_per_product | 
| -----------------------------------------------: | -------------------------------: | 
| Electrical Equipment and Machinery               | 891050.7273                      | 
| Automobiles & Components                         | 35373.4795                       | 
| "Pharmaceuticals, Biotechnology & Life Sciences" | 24162.0000                       | 
| Capital Goods                                    | 7391.7714                        | 
| Materials                                        | 3208.8611                        |         

## 3. Questions to Research:
#### 3.1. Which products contribute the most to carbon emissions? 

```
SELECT 
    product_name, 
    SUM(carbon_footprint_pcf) AS total_carbon_footprint
FROM product_emissions
GROUP BY product_name
ORDER BY total_carbon_footprint DESC
LIMIT 5;
```

| product_name                 | total_carbon_footprint | 
| ---------------------------: | ---------------------: | 
| Wind Turbine G128 5 Megawats | 3718044                | 
| Wind Turbine G132 5 Megawats | 3276187                | 
| Wind Turbine G114 2 Megawats | 1532608                | 
| Wind Turbine G90 2 Megawats  | 1251625                | 
| TCDE                         | 198150                 |  

#### 3.2. What are the industry groups of these products?
```
SELECT 
    pe.product_name, 
    ig.industry_group
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
WHERE pe.product_name IN (
    'Wind Turbine G128 5 Megawats',
    'Wind Turbine G132 5 Megawats',
    'Wind Turbine G114 2 Megawats',
    'Wind Turbine G90 2 Megawats',
    'TCDE'
);
```

| product_name                 | industry_group                     | 
| ---------------------------: | ---------------------------------: | 
| Wind Turbine G90 2 Megawats  | Electrical Equipment and Machinery | 
| Wind Turbine G114 2 Megawats | Electrical Equipment and Machinery | 
| Wind Turbine G128 5 Megawats | Electrical Equipment and Machinery | 
| Wind Turbine G132 5 Megawats | Electrical Equipment and Machinery | 
| TCDE                         | Materials                          | 
| TCDE                         | Materials                          |         


#### 3.3. What are the industries with the highest contribution to carbon emissions?
```
SELECT 
    ig.industry_group,
    SUM(pe.carbon_footprint_pcf) AS total_carbon_footprint
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
GROUP BY ig.industry_group
ORDER BY total_carbon_footprint DESC
LIMIT 5;
```

| industry_group                     | total_carbon_footprint | 
| ---------------------------------: | ---------------------: | 
| Electrical Equipment and Machinery | 9801558                | 
| Automobiles & Components           | 2582264                | 
| Materials                          | 577595                 | 
| Technology Hardware & Equipment    | 363776                 | 
| Capital Goods                      | 258712                 |         

#### 3.4. What are the companies with the highest contribution to carbon emissions?
```
SELECT 
    c.company_name,
    SUM(pe.carbon_footprint_pcf) AS total_carbon_footprint
FROM product_emissions pe
JOIN companies c ON pe.company_id = c.id
GROUP BY c.company_name
ORDER BY total_carbon_footprint DESC
LIMIT 5;
```

| company_name                            | total_carbon_footprint | 
| --------------------------------------: | ---------------------: | 
| "Gamesa Corporación Tecnológica, S.A."  | 9778464                | 
| Daimler AG                              | 1594300                | 
| Volkswagen AG                           | 655960                 | 
| "Mitsubishi Gas Chemical Company, Inc." | 212016                 | 
| "Hino Motors, Ltd."                     | 191687                 |

#### 3.5. What are the countries with the highest contribution to carbon emissions?
```
SELECT 
    co.country_name,
    SUM(pe.carbon_footprint_pcf) AS total_carbon_footprint
FROM product_emissions pe
JOIN countries co ON pe.country_id = co.id
GROUP BY co.country_name
ORDER BY total_carbon_footprint DESC
LIMIT 5;
```

| country_name | total_carbon_footprint | 
| -----------: | ---------------------: | 
| Spain        | 9786130                | 
| Germany      | 2251225                | 
| Japan        | 653237                 | 
| USA          | 518381                 | 
| South Korea  | 186965                 |        

#### 3.6. What is the trend of carbon footprints (PCFs) over the years?
```
SELECT 
    year,
    AVG(carbon_footprint_pcf) AS avg_carbon_footprint
FROM product_emissions
GROUP BY year
ORDER BY year;
```

| year | avg_carbon_footprint | 
| ---: | -------------------: | 
| 2013 | 2399.3190            | 
| 2014 | 2457.5827            | 
| 2015 | 43188.9044           | 
| 2016 | 6891.5210            | 
| 2017 | 4050.8452            |       

#### 3.7. Which industry groups has demonstrated the most notable decrease in carbon footprints (PCFs) over time?
```
SELECT 
    ig.industry_group,
    MAX(pe.carbon_footprint_pcf) - MIN(pe.carbon_footprint_pcf) AS carbon_footprint_reduction
FROM product_emissions pe
JOIN industry_groups ig ON pe.industry_group_id = ig.id
GROUP BY ig.industry_group
ORDER BY carbon_footprint_reduction DESC
LIMIT 5;

```

| industry_group                     | carbon_footprint_reduction | 
| ---------------------------------: | -------------------------: | 
| Electrical Equipment and Machinery | 3718044                    | 
| Automobiles & Components           | 191581                     | 
| Materials                          | 167000                     | 
| Capital Goods                      | 87589                      | 
| "Food, Beverage & Tobacco"         | 26836                      |   
***
# 4. Conclusions and Insights
### 4.1. Heavy Industry Dominance in Carbon Emissions:

* Products associated with heavy industry, such as wind turbines and office chairs, exhibit some of the highest levels of carbon emissions.
* This highlights the significant environmental impact of industrial manufacturing processes, particularly those involving large-scale machinery and materials.
***
### 4.2. Carbon Emissions in Automobile Manufacturing:

* Certain car models, including Land Cruiser Prado, Mercedes-Benz GLA, S-Class, and SL, stand out for their substantial carbon emissions during production.
* Automobile manufacturing processes, which often involve complex assembly lines and extensive use of materials, contribute significantly to overall carbon footprints.
***
### 4.3. Surprising Role of Pharmaceuticals Industry:

* The "Pharmaceuticals, Biotechnology & Life Sciences" industry ranks prominently, occupying the 7th place in terms of carbon emissions.
* This revelation sheds light on the environmental footprint associated with pharmaceutical production, challenging perceptions about the sector's sustainability practices.
***
### 4.4. Carbon Footprint Variability Across Industries:

* Industries vary significantly in their carbon footprint per product, reflecting differences in manufacturing methods, materials used, and energy sources.
* Understanding these variations can inform targeted sustainability efforts tailored to specific industries, maximizing environmental benefits.
***
### 4.5. Global Distribution of Carbon Emissions:

* Certain countries, such as Spain, Germany, Japan, the USA, and South Korea, emerge as leading contributors to carbon emissions.
* This underscores the need for international cooperation and coordinated efforts to address climate change on a global scale.
***
### 4.6. Trends in Carbon Footprints Over Time:

* Analysis of carbon footprints over the years reveals fluctuations, potentially influenced by economic factors, technological advancements, and regulatory changes.
* Monitoring these trends provides valuable insights for policymakers and industry stakeholders seeking to implement effective strategies for carbon reduction.
