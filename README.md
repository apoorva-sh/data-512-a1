# DATA 512 A1: Data Curation

## Project Goal

The goal of this project is to incorporate best practices in data collection and analysis, such as reproducability and clarity on steps taken to collect and analyse data. This project aims to showcase these practices using wikipedia traffic data from January 1 2008 through September 30 2018.

## API Documentation
Two APIs have been used in this project:

- [Legacy pagecount(monthly)](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts#Pagecounts) | [endpoint](https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)

- [Pageview (monthly)](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews#Monthly_counts) | [endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)

## License

- The Source Code is under the [MIT License](https://github.com/apoorva-sh/data-512-a1/blob/master/LICENSE)

- Link to Wikimedia [Terms of Use](https://foundation.wikimedia.org/wiki/Terms_of_Use/en)

## Data Files

The Data Files present in this repo are of two types:

- **.json data files:** These files contain the page views/counts for different sites or access-sites for a specific API in .json format. These files also contain the timestamp for the views/counts, along with details on the type of site/access-site and the agent used to generate the view/count value

- **.csv data file:** This file contains the final data that is analyzed in the source code. This data has the following columns:

| Column Name | Column Type | Value contained|
|--------------|-------------|---------------|
| pagecount_desktop_views | float64 | Number of desktop page view counts (from Legacy API) |
| pagecount_mobile_views | float64 | Number of mobile page views counts (from Legacy API) |
| pagecount_all_views | float64 | Total number of page views counts (from Legacy API) |
| pageview_mobile_views | float64 | Number of mobile page views (from Page View API) |
| pageview_desktop_views | float64 | Number of desktop page views (from Page View API) |
| pageview_all_views | float64 | Total number of page views (from Page View API) |
| year | object | specific Year of a record in yyyy format |
| month | object | specific Month of a record in mm format |

## Special Considerations

- This project does not consider spyder scraped data when getting page view information using the PageView API, however spyder data could not be avoided in the Legacy data
- The range of time for analysis has been hard coded into this project, for change in range you would have to change all the start and end values in every get_data() function
