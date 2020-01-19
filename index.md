---
title: "Developing Data Product"
subtitle: "Week 4 Assignment"
author: "Nur Seto Dimas"
date: "19 January 2020"
output: 
  ioslides_presentation: 
    highlight: haddock
    keep_md: yes
    smaller: yes
---



## About The Project

This dashboard project utilize [flexdashboard](https://rmarkdown.rstudio.com/flexdashboard/index.html) to create interactive visualization on Avocado Data Set from [kaggle](https://www.kaggle.com/neuromusic/avocado-prices).

**Features description**  
1. Price, displays plot visualization on avocado average price from year 2015-2018 grouped by type(conventional and organic).  
2. Search, by default this will display avocado average price grouped by type(conventional and organic) then region. The region can be chosen via drop down menu. The plot then will adjust its visual according to region selected


All plot displayed generated with plotly.

## Overview on Data set

This data was downloaded from the Hass Avocado Board website in May of 2018 & compiled into a single CSV. Here's how the Hass Avocado Board describes the data on their website.

Some relevant columns in the data set:

* Date - The date of the observation
* AveragePrice - the average price of a single avocado
* type - conventional or organic
* year - the year
* Region - the city or region of the observation
* Total Volume - Total number of avocados sold
* 4046 - Total number of avocados with PLU 4046 sold
* 4225 - Total number of avocados with PLU 4225 sold
* 4770 - Total number of avocados with PLU 4770 sold

## Plot


```r
plot_ly(data = type_tibble, 
        x = ~Date, y = ~AveragePrice, color = ~type, 
        mode = "lines+markers") %>%
        layout(title = "Average Avocado Price by Type",
               xaxis = list(title = "Year"),
               yaxis = list(title = "Average Price"))
```

## Plot





<!--html_preserve--><div id="htmlwidget-6aedec5cbc34d26dc2c9" style="width:720px;height:432px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-6aedec5cbc34d26dc2c9">{"x":{"visdat":{"29287f4f4f8e":["function () ","plotlyVisDat"]},"cur_data":"29287f4f4f8e","attrs":{"29287f4f4f8e":{"x":{},"y":{},"mode":"lines+markers","color":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20]}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"Average Avocado Price by Type","xaxis":{"domain":[0,1],"automargin":true,"title":"Year"},"yaxis":{"domain":[0,1],"automargin":true,"title":"Average Price"},"hovermode":"closest","showlegend":true},"source":"A","config":{"showSendToCloud":false},"data":[{"x":["2015-01-04","2015-02-01","2015-03-01","2015-04-05","2015-05-03","2015-06-07","2015-07-05","2015-08-02","2015-09-06","2015-10-04","2015-11-01","2015-12-06","2016-01-03","2016-02-07","2016-03-06","2016-04-03","2016-05-01","2016-06-05","2016-07-03","2016-08-07","2016-09-04","2016-10-02","2016-11-06","2016-12-04","2017-01-01","2017-02-05","2017-03-05","2017-04-02","2017-05-07","2017-06-04","2017-07-02","2017-08-06","2017-09-03","2017-10-01","2017-11-05","2017-12-03","2018-01-07","2018-02-04","2018-03-04"],"y":[1.22,0.99,0.99,1.16,1.2,1.07,1.35,1.45,1.11,1.31,1.02,1.08,1.03,1.07,1.27,0.85,1.03,1.47,1.42,1.48,1.44,1.51,1.63,1.48,1.47,1.49,1.18,1.62,1.47,1.7,1.56,1.53,1.76,1.69,1.62,1.39,1.13,1.03,1.08],"mode":"lines+markers","type":"scatter","name":"conventional","marker":{"color":"rgba(102,194,165,1)","line":{"color":"rgba(102,194,165,1)"}},"textfont":{"color":"rgba(102,194,165,1)"},"error_y":{"color":"rgba(102,194,165,1)"},"error_x":{"color":"rgba(102,194,165,1)"},"line":{"color":"rgba(102,194,165,1)"},"xaxis":"x","yaxis":"y","frame":null},{"x":["2015-01-04","2015-02-01","2015-03-01","2015-04-05","2015-05-03","2015-06-07","2015-07-05","2015-08-02","2015-09-06","2015-10-04","2015-11-01","2015-12-06","2016-01-03","2016-02-07","2016-03-06","2016-04-03","2016-05-01","2016-06-05","2016-07-03","2016-08-07","2016-09-04","2016-10-02","2016-11-06","2016-12-04","2017-01-01","2017-02-05","2017-03-05","2017-04-02","2017-05-07","2017-06-04","2017-07-02","2017-08-06","2017-09-03","2017-10-01","2017-11-05","2017-12-03","2018-01-07","2018-02-04","2018-03-04"],"y":[1.79,1.83,1.76,1.93,2.03,1.93,2.04,2,1.86,1.98,1.88,1.84,1.75,1.81,1.92,1.56,1.78,1.47,1.43,1.67,1.73,1.73,1.93,1.97,1.87,1.72,1.84,1.86,1.79,1.63,2.03,1.98,2,1.59,1.5,1.44,1.54,1.52,1.48],"mode":"lines+markers","type":"scatter","name":"organic","marker":{"color":"rgba(141,160,203,1)","line":{"color":"rgba(141,160,203,1)"}},"textfont":{"color":"rgba(141,160,203,1)"},"error_y":{"color":"rgba(141,160,203,1)"},"error_x":{"color":"rgba(141,160,203,1)"},"line":{"color":"rgba(141,160,203,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

