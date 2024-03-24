## 💼 Project: Carbon Emission Analysis
# 1.Introduction
This report aims to analyze carbon emissions to examine the carbon footprint across various industries. We aim to identify sectors with the highest levels of emissions by analyzing them across countries and years, as well as to uncover trends.

Carbon emissions play a crucial role in the environment, accounting for over 75% of global emissions and posing a significant environmental challenge. These emissions contribute to the accumulation of greenhouse gases in the atmosphere, leading to climate change, planetary warming, and involvement in various environmental disasters.

Through this analysis, we hope to gain an understanding of the environmental impact of different industries and contribute to making informed decisions in sustainable development.

### Data Source: Where Our Data Comes From
Our dataset is compiled from publicly available data from nature.com and encompasses the product carbon footprints (PCF) for various companies. PCFs represent the greenhouse gas emissions associated with specific products, quantified in CO2 (carbon dioxide equivalent).

### Data Structure
The dataset consists of 4 tables containing information regarding carbon emissions generated during the production of goods.
![image](https://github.com/29AT20/SQL-Carbon-Emission-Analysis-Practice/assets/108121672/73331c48-8713-42aa-9d8e-7c846e5dfc2a)

### Tables' columns description

***

#### **1. Table 'product_emissions':**
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

#### **2. Table 'industry_groups':**
**id:** Unique identifier for each industry group.

**industry_group:** The name of the industry group, categorizing businesses within similar sectors based on their products or services offered.
 

***

#### **3. Table 'companies':**
**id:** Unique identifier for each company.

**company_name:** The name of the company, identifying the specific organization within the dataset.
 

#### **4. Table 'countries':**
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
### 1.1. Table 'product_emissions'

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

***
### 1.2. Table 'industry_groups'
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

***
### 1.3 Table 'companies'
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

***
### 1.4. Table 'countries'
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
### 2.1. Top 5 average carbon footprint per year:
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

***
### 2.2.  Top 5 countries with total carbon footprint 
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

***
### 2.3. Top 5 industries with the highest average carbon footprint per product
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

***
## 3. Questions to Research:
### 3.1. Which products contribute the most to carbon emissions? 

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
***
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
***
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
***
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
***
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
***
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
***
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
