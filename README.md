-- region average price year

SELECT region, avg(AveragePrice) avocado_price, year

FROM `reflecting-poet-391612.project.avocado`

where year between 2015 and 2017

group by year, region 
order by year, avocado_price;

-- average avocado price per month

SELECT 
  month, year,
  avg(AveragePrice) AveragePrice,
  case
    when month = 1 then "january"
    
    when month = 2 then "febuary"
    
    when month = 3 then "March"
    
    when month = 4 then "april"
    
    when month = 5 then "may"
    
    when month = 6 then "june"
    
    when month = 7 then "july"
    
    when month = 8 then "august"
    
    when month = 9 then "september"
    
    when month = 10 then "october"
    
    when month = 11 then "november"
    
    else "december"
  end as months_name

FROM `reflecting-poet-391612.project.avocado` 

where year between 2015 and 2017

group by year, month
order by year, month;


--what's the peak month for avocado sales

SELECT 
  month, year,
  sum(small_bags +large_bags + XLarge_Bags) as sales_per_month,
  case
    when month = 1 then "january"
    
    when month = 2 then "febuary"
    
    when month = 3 then "March"
    
    when month = 4 then "april"
    
    when month = 5 then "may"
    
    when month = 6 then "june"
    
    when month = 7 then "july"
    
    when month = 8 then "august"
    
    when month = 9 then "september"
    
    when month = 10 then "october"
    
    when month = 11 then "november"
    
    else "december"
  end as months_name

FROM `reflecting-poet-391612.project.avocado` 

where year between 2015 and 2017

group by year, month
order by year,month;


--avocado sales per region

SELECT region, year, 
  sum(Small_Bags) total_small_bags_sales,
  sum(Large_Bags) total_large_bags_sales,
  sum(XLarge_Bags) total_xlarge_bags_sales,
  
FROM `reflecting-poet-391612.project.avocado`
where year between 2015 and 2017 
group by region, year
