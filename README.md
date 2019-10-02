# DATA512 A1 Data Curation

## Overview
This is the project of collecting and visualizing Wikimedia monthly traffic. It contains the data collection, data processing, and data visualization steps. The repository contains source code, raw data, processed data, and final deliverable, a traffic graph for all sources of Wikimedia from 2008 to 2019.

## Goal
The goal of this project is to prepare for open scientific research best practice in designing and implementing your project, and make sure the project can be fully reproducible by others.

## Data sources
Wikipedia traffic from 2008-2019, using two different API endpoints, the Legacy Pagecounts API and the Pageviews API.

 - [The Legacy Pagecounts API] (https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end) provides access to desktop and mobile traffic data from December 2007 through July 2016.
- [The Pageviews API] (https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through last month.
 
## Repository structure 
 
 ```
  |-- hcds-a1-data-curation.ipynb
  |-- En-wikipedia_traffic_200801-201909_ywei1.png
  |-- README.md
  |-- LISCENSE
  |-- raw_output
  |   |- pagecounts_desktop-site_200712-201908.json
  |   |- pageviews_mobile-app_200712-201908.json
  |   |- pagecounts_mobile-site_200712-201908.json
  |   |- pageviews_mobile-web_200712-201908.json
  |   |- pageviews_desktop_200712-201908.json
  |-- en-wikipedia_traffic_200712-201908.csv

  1 directory, 10 files
 ```

## Data Schema 
| Column  | Description |
| ------------- | ------------- |
| year  | Year of data (YYYY)  |
| month  | Month of Data (MM)  |
| pagecount_all_views  | Sum of desktop and mobile page counts on Wiki based on legacy API   |
| pagecount_desktop_views  | Sum of desktop views based on legacy API  |
| pagecount_mobile_views  | Sum of mobile views based on legacy pagecount API  |
| pageview_all_views  | Sum of desktop and mobile views based on pageviews API   |
| pageview_desktop_views  | Sum of desktop views based on pageviews API  |
| pageview_mobile_views  | Sum of mobile views based on pageviews API  |

## Data Visualization
![alt text](https://github.com/davidweinfls/data-512-a1/blob/master/En-wikipedia_traffic_200801-201909_ywei1.png)

## License of source data
- [Wikimedia](https://foundation.wikimedia.org/wiki/Terms_of_Use/en)
- [MIT](https://opensource.org/licenses/MIT)

## Known Issues
For this project, I excluded web crawler and bot traffic since I only focus on organic traffic. There's a `agent=user` setting in Pageview API which has been turned on exactly for this purpose.
