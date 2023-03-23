# Project 2: ETL Mini Project

## Proposal

  ### Research Question
  
   🏡 Are evictions in NYC related to demographic variables (i.e. gender, ethnicity, public assistance)? 

  ### Two sources of data
  
   **1. Evictions:** https://catalog.data.gov/dataset/evictions
   
   **2. Demographics:** https://catalog.data.gov/dataset/demographic-statistics-by-zip-code

  ### Type of final production database to load the data into (relational or non-relational)
  
   * Relational – we used SQLite as our final production database to load the data into.
  
  ### Relevant and succinct description of findings (2–3 sentences)
  
   * According to the graph of Total Evictions vs. PERCENT RECEIVES PUBLIC ASSISTANCE, you are less likely to be evicted if you recieve public assistance.
   
   * Looking at the relationship between gender and evictions in NYC, it's clear that men are more likely to be evicted. 
   
   * With reference to the graph, we see that in the Brox and Manhattan, there is a large number of minorities being evicted. 
  
## Report

  ### Extract
  
   * The original data sources are csv files. They were zipcode-level, aggragated data. 
  
  ### Transform
  
   * For the demographics data, we chose the columns with the zip code, number of participants, percentages of gender, ethnicity, and people on government assistance because those are the factors with want to explore. We then dropped duplicates and any zip code with less than 20 participants because those zip codes are not properly represented. With the cleaned demographics data, we created a column called PERCENT MINORITY by adding all the percentages of the non-white ethnicities. For the evictions data, we only extracted the zip code, eviction date, and the type of eviction (Residential or Commercial). Then, we filtered for only Residential evictions because we think that they will have a stronger relationship with the demographics data. After that, we created a data frame with the total amount of evictions by zip code. With the two new data frames, we performed an inner join on zip code to create the final data frame.
  
  ### Load

   * Explain the final database, tables/collections, and why the topic was chosen at a professional level
