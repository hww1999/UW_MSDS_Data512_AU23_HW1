# UW_MSDS_Data512_Au23_HW1

# Goal of the Project

The goal of the project is to visualize the article traffic of award winning movies between 2015 and 2023. The list of the articles comes from [this Google Sheet](https://docs.google.com/spreadsheets/d/1A1h_7KAo7KXaVxdScJmIVPTvjb3IuY9oZhNV4ZHxrxw/edit#gid=1229854301)

# License Used

The source data (licenses) used in the project is a PageViews API called Wikimedia Foundation REST API: [terms of use](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions), with its [documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) and [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end).

# Fields of Data Files

## Intermediary data files (inter_ACCESS_startYYYYMM-endYYYYMM.json) include fields of:

project: source of the data (en.wikipedia in this case),
article: name of the article, 
granularity: the frequency based on which the data we are extracting (monthly in this case),
timestamp: the timestamp of the data extracted from (formatted as YYYYMMDD00 for API use),
access: from which platform the data is sourced from, (desktop/mobile-web/mobile-app in this case),
agent: how the API is extracting (user in this case),
views: the number of views of the article on the platform during the specific timestamp (integer)

## Final output files include fields of (academy_monthly_ACCESS_startYYYYMM-endYYYYMM.json) :

article: name of the article, 
timestamp: the timestamp of the data extracted from (formatted as YYYY-MM-DD after cleaning up),
views: the number of views of the article on the platform during the specific timestamp (integer)

# Known issues/special considerations

for now, there exists movies in the list of articles that have no data from the PageViews API we used.

```bash
.
├── LICENSE
├── README.md
├── data
│   ├── data processing.ipynb
│   ├── data scrape.ipynb
│   ├── final json files
│   │   ├── academy_monthly_cumulative_start201507-end202310.json
│   │   ├── academy_monthly_desktop_start201507-end202310.json
│   │   └── academy_monthly_mobile_start201507-end202310.json
│   └── intermediary json files
│       ├── inter_desktop_start201507-end202310.json
│       ├── inter_mobile_app_start201507-end202310.json
│       └── inter_mobile_web_start201507-end202310.json
└── visualization
    ├── FewestMonthData.png
    ├── MinAvg.png
    ├── MinMaxAvg.png
    ├── Top10PeakViews.png
    └── data visualization.ipynb
```
# Visualizations

![MinMaxAvg](https://github.com/hww1999/data-512-homework_1/assets/50925030/840e3cd2-4855-4d29-b541-b2ae1499ba0b)

The MinAvg is intended to view the articles that have the minimum average views on desktop and mobile accesses.
![MinAvg](https://github.com/hww1999/data-512-homework_1/assets/50925030/2ddef64f-7e93-499e-aaa4-de9ada506469)

![Top10PeakViews](https://github.com/hww1999/data-512-homework_1/assets/50925030/29f24376-16a6-430c-bcce-2589e720d03a)

![FewestMonthData](https://github.com/hww1999/data-512-homework_1/assets/50925030/a1b1ecc6-c499-456a-bffd-5865ffab8b46)


