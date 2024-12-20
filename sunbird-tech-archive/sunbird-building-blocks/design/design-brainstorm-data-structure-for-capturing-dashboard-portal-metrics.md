---
icon: elementor
---

# \[Design-Brainstorm]-Data-structure-for-capturing-dashboard-portal-metrics

#### Background

The portal landing pages should serve dashboards with relevant metrics in order to communicate the reach and impact of the DIKSHA program. The dashboards are required for the MHRD launch in Jan 2019.

#### Problem Statement

The dashboard requires various static and dynamically computed metrics. This design brainstorm needs to define a JSON data structure to serve the data for the various requirements for the dashboard. The metrics that need to be computed for the portal dashboards are defined below. Also, the dashboard metrics will have to support drill down by State to which the data belongs to.

1. Total number of unique devices till date across portal and mobile app that have access Diksha.
2. Total number of content play sessions till date across portal and mobile app.
3. Total time spent on Diksha (i.e. total session time) till date across portal and mobile app.

#### Solution

Cumulative SummariesCumulative summaries can be generated by using the data from the workflow\_usage\_summary\_fact cassandra table.&#x20;

1. noOfUniqueDevices: This metric can be computed by filtering out records with d\_period = 0 (cumulative), d\_device\_id = 'all' and summing up the m\_total\_devices\_count field.
2. totalContentPlaySessions: This metric can be computed by filtering out records with d\_period = 0 (cumulative), d\_type = 'content', d\_mode = 'play' and summing up the m\_total\_sessions field.
3. totalTimeSpent: This metric can be computed by filtering out records with d\_period = 0 (cumulative), d\_device\_id = 'all' and summing up on m\_total\_ts field.
4. totalDigitalContentPublished: This metric can be computed from the search api. We need to use the composite search API /composite/v3/search and filter by contentType Resource to get a count of total number of live content.&#x20;

```js
{
  "eid":"ME_DASHBOARD_CUMULATIVE_SUMMARY",
  "ets":1535417736822,
  "syncts":1535390695986,
  "metrics_summary":{
    "noOfUniqueDevices":100,
    "totalDigitalContentPublished":400,
    "totalContentPlaySessions":200,
    "totalTimeSpent":500.96,
    "telemetryVersion":"3.0"
  }
}
```

The cumulative summary files will be uploaded to cloud storage using Secor. The sunbird platform team will pull the cumulative summary file from the cloud storage. There will be a new file generated everyday with the date appended to the file name.

***

\[\[category.storage-team]] \[\[category.confluence]]
