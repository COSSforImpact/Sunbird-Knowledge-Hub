---
icon: elementor
---

# Data-Products-and-Owners

This page details the list of various Data products like ETL jobs, Report Jobs, Exhaust Jobs, Adhoc Scripts.

How to build and run dataproducts is detailed in \[\[Data products - Build And Run|Data-products---Build-And-Run]]

| **Script Name**                                                                                                                                                                                             | **Owner**        | **Current Repo**                                                                                               | **Description**                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| exhaust / ProgressExhaustJob                                                                                                                                                                                | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Generate progress reports of each enrolled user for the course batch                                                                                                            |
| exhaust / ResponseExhaustJob                                                                                                                                                                                | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Generate reports to identify each enrolled users response to each content on the course                                                                                         |
| exhaust / UserInfoExhaustJob                                                                                                                                                                                | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Generate reports to get the all enrolled users on the course                                                                                                                    |
| exhaust / BaseReportJob                                                                                                                                                                                     | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Base class for data-products scripts                                                                                                                                            |
| exhaust / BaseCollectionExhaustJob                                                                                                                                                                          | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Base class for exhaust jobs                                                                                                                                                     |
| job / CourseEnrollmentJob                                                                                                                                                                                   | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Generate report for enrolment details on the course batch                                                                                                                       |
| job / CourseConsumptionJob                                                                                                                                                                                  | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Generate report for consumption metrics on the course batch                                                                                                                     |
| audit / CollectionSummaryJobV2                                                                                                                                                                              | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Updates collection-summary-snashot druid data source                                                                                                                            |
| audit / CourseBatchStatusUpdaterJob                                                                                                                                                                         | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Updates course batch es index                                                                                                                                                   |
| updater / CassandraMigratorJob                                                                                                                                                                              | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Migration script add the user\_enrolments data report cluster’s user\_enrolments table                                                                                          |
| job / StateAdminReportJob                                                                                                                                                                                   | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Provides organisation wise consent details                                                                                                                                      |
| job / StateAdminGeoReportJob                                                                                                                                                                                | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Provides Organisation wise district, block, school count and district wise block, school count                                                                                  |
| etl-jobs / analytics / UserCacheIndexer                                                                                                                                                                     | Sunbird-Lern     | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Updates the user redis cache data with user and location from cassandra                                                                                                         |
| job / AssessmentCorrectionJob                                                                                                                                                                               | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Assessment score correction for batches                                                                                                                                         |
| audit / CollectionReconciliationJob                                                                                                                                                                         | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Updating completion dates, enrolment dates and certificate details                                                                                                              |
| audit / AssessmentScoreCorrectionJob                                                                                                                                                                        | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Assessment score correction for batches                                                                                                                                         |
| audit / ScoreMetricMigrationJob                                                                                                                                                                             | Diksha           | [Sunbird-Lern](https://github.com/Sunbird-Lern)/[data-products](https://github.com/Sunbird-Lern/data-products) | Migration job to correct and add updated attempt details in assessment\_aggregator table                                                                                        |
| pythonscripts / content\_consumption                                                                                                                                                                        | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Consumption of contents for last week and last 6 months as two report files                                                                                                     |
| pythonscripts / ecg\_learning                                                                                                                                                                               | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Trend graph of http request count in Diksha environment for last 7 days                                                                                                         |
| job / ETBMetricsJob                                                                                                                                                                                         | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Generate report for textbook and dialcode for collection and dialcode level.                                                                                                    |
| pythonscripts / [landing\_page.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/landing\_page.py)               | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Generates overall consumption report for each state. This report is used in tenant based landing pages. This pulls data from daily metrics and year wise uploads data into blob |
| pythonscripts / [cmo\_dashboard.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/cmo\_dashboard.py)             | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Generates daily content play report to respective tenant                                                                                                                        |
| pythonscripts / [content\_consumption.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/content\_consumption.py) | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Generates overall and last week report for each content consumption along with textbook details                                                                                 |
| sourcing / ContentDetailsReport                                                                                                                                                                             | Sunbird-CoCreate | Sunbird-Ed/sunbird-data-products                                                                               | Generate reports for the collections and content associated to it for the VDN program                                                                                           |
| sourcing / FunnelReport                                                                                                                                                                                     | Sunbird-CoCreate | Sunbird-Ed/sunbird-data-products                                                                               | Generate reports for program contributors and contributions for contents.                                                                                                       |
| sourcing / SourcingMetrics                                                                                                                                                                                  | Sunbird-CoCreate | Sunbird-Ed/sunbird-data-products                                                                               | Generate both the reports for collection and folder level of contributed contents in VDN.                                                                                       |
| sourcing / SourcingSummaryReport                                                                                                                                                                            | Sunbird-CoCreate | Sunbird-Ed/sunbird-data-products                                                                               | Sourcing Summary Report                                                                                                                                                         |
| data-products / TextbookProgressJob                                                                                                                                                                         | Diksha           | Sunbird-Ed/sunbird-data-products                                                                               | Tenant level report on textbook creation progress                                                                                                                               |
| pythonscripts / druid\_job\_submitter                                                                                                                                                                       | Sunbird-Obsrv    | Sunbird-Ed/sunbird-data-products                                                                               | Submit the Druid query processor reports(hawk eye reports) based on the scheduler                                                                                               |
| [druid\_anomaly\_detection.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/anomaly-detection/src/main/python/druid\_anomaly\_detection.py)                                      | Sunbird-Obsrv    | Sunbird-Ed/sunbird-data-products                                                                               | Script to set scheduler to find data anomaly between druid data                                                                                                                 |
| [data\_replay.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/replay-scripts/src/main/python/replay/data\_replay.py)                                                            | Sunbird-Obsrv    | Sunbird-Ed/sunbird-data-products                                                                               | Script to replay and index the incorrect data in druid for a timerange                                                                                                          |
| etl-jobs / CSVToRedisIndexer                                                                                                                                                                                | Sunbird-Obsrv    | Sunbird-Ed/sunbird-data-products                                                                               | Script to index data from CSV file to specified redis                                                                                                                           |
| data-products / [BaseUCIExhaustJob](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/data-products/src/main/scala/org/sunbird/analytics/exhaust/uci/BaseUCIExhaustJob.scala)         | Sunbird-UCI      | Sunbird-Ed/sunbird-data-products                                                                               | Base Exhaust job for UCI Private and Response Exhaust                                                                                                                           |
| data-products / [UCIPrivateExhaustJob](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/data-products/src/main/scala/org/sunbird/analytics/exhaust/uci/UCIPrivateExhaustJob.scala)   | Sunbird-UCI      | Sunbird-Ed/sunbird-data-products                                                                               | Create password protected zip file using an encryption key with conversation id, conversation name, device id, and phone number (if consent is given)                           |
| data-products / [UCIResponseExhaustJob](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/data-products/src/main/scala/org/sunbird/analytics/exhaust/uci/UCIResponseExhaustJob.scala) | Sunbird-UCI      | Sunbird-Ed/sunbird-data-products                                                                               | <ul><li>Based on user consent, provide question response data if consent is true else send empty value in output csv.</li></ul>                                                 |

|

### Adhoc Scripts

| **Script Name**                                                                                                                                                               | **Owner**     | **Current Repo**                 | **Description**                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [CourseDataMigration.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/CourseDataMigration.scala)                   | Sunbird-Lern  | Sunbird-Ed/sunbird-data-products | Script to migrate valid content\_consumption to user\_content\_consumption table and user\_courses to user\_enrolments in cassandra |
| [CourseStatusUpdater.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/CourseStatusUpdater.scala)                   | Sunbird-Lern  | Sunbird-Ed/sunbird-data-products | Updates course consumption data in Cassandra with failed or non processed events.                                                   |
| [DedupAnalyzer.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/DedupAnalyzer.scala)                               | Sunbird-Obsrv | Sunbird-Ed/sunbird-data-products | Script to get duplicated events analysis report                                                                                     |
| [ExtractMissingEvents.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/ExtractMissingEvents.scala)                 | Sunbird-Obsrv | Sunbird-Ed/sunbird-data-products | Script to get missing events compared between ingest and raw events bucket                                                          |
| [DikshaLoadAnalysis.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/DikshaLoadAnalysis.scala)                     | Diksha        | Sunbird-Ed/sunbird-data-products | Script to get Diksha consumption analysis report                                                                                    |
| [DistrictMappingMisMatch.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/DistrictMappingMisMatch.scala)           | Diksha        | Sunbird-Ed/sunbird-data-products | Script to updated user’s location data in device profile table                                                                      |
| [LocationPopupAnalysis.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/LocationPopupAnalysis.scala)               | Diksha        | Sunbird-Ed/sunbird-data-products | Script to get the count of location popup events for analysis purpose                                                               |
| [ProcessFailedEvents.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/ProcessFailedEvents.scala)                   | Diksha        | Sunbird-Ed/sunbird-data-products | Scipt to reprocess failed events and push to kafka                                                                                  |
| [ProcessLPEvents.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/ProcessLPEvents.scala)                           | Diksha        | Sunbird-Ed/sunbird-data-products | Script to push events to kafka topic to reprocess                                                                                   |
| [ProcessPortalEvents.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/ProcessPortalEvents.scala)                   | Diksha        | Sunbird-Ed/sunbird-data-products | Script to push events to kafka topic to reprocess                                                                                   |
| [PushToKafka.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/PushToKafka.scala)                                   | Diksha        | Sunbird-Ed/sunbird-data-products | Script to push events to kafka topic to index in druid                                                                              |
| [ReplayExtractorFailedEvents.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/ReplayExtractorFailedEvents.scala)   | Diksha        | Sunbird-Ed/sunbird-data-products | Script to push events to kafka topic to reprocess                                                                                   |
| [UserDeclaredLocationAnalysis.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/UserDeclaredLocationAnalysis.scala) | Diksha        | Sunbird-Ed/sunbird-data-products | Script to get count of users whose location is stamped properly to telemetry event                                                  |

#### Deprecated

| **Script Name**                                                                                                                                                                                                                             | **Owner**  | **Current Repo**                 | **Description**                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [S3CheckPointAnalysis.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/S3CheckPointAnalysis.scala)                                                                               | Deprecated | Sunbird-Ed/sunbird-data-products | Script to get data count for analysis purpose                                                                                   |
| [UserOrgDataMigration.scala](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/adhoc-scripts/src/main/scala/UserOrgDataMigration.scala)                                                                               | Deprecated | Sunbird-Ed/sunbird-data-products | Script to migrate user\_org to user\_organisation table in cassandra                                                            |
| etl-jobs / ESCloudUploader                                                                                                                                                                                                                  | Deprecated | Sunbird-Ed/sunbird-data-products | Script to get and upload data as json file from Elasticsearch to Cloud store                                                    |
| etl-jobs / ESRedisIndexer                                                                                                                                                                                                                   | Deprecated | Sunbird-Ed/sunbird-data-products | Script to index data from Elasticsearch to specified redis                                                                      |
| etl-jobs / DeviceProfileUpdateCassandra                                                                                                                                                                                                     | Deprecated | Sunbird-Ed/sunbird-data-products | Script to get and add it in new device profile table                                                                            |
| pythonscripts / user\_declaration\_report                                                                                                                                                                                                   | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala                                                                                                   |
| pythonscripts / user\_detail\_report                                                                                                                                                                                                        | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala                                                                                                   |
| pythonscripts / [course\_enrolments.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/tpd/course\_enrolments.py)                                             | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala as job / CourseEnrollmentJob                                                                      |
| pythonscripts / [course\_consumption.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/tpd/course\_consumption.py)                                           | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala as job / CourseConsumptionJob                                                                     |
| pythonscripts / [district\_monthly.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/location/district\_monthly.py)                                          | deprecated | Sunbird-Ed/sunbird-data-products | Deprecated since implemented through Hawkeye                                                                                    |
| pythonscripts / [district\_weekly.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/location/district\_weekly.py)                                            | deprecated | Sunbird-Ed/sunbird-data-products | Deprecated since implemented through Hawkeye                                                                                    |
| pythonscripts / [content\_progress.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/etb/content\_progress.py)                                               | deprecated | Sunbird-Ed/sunbird-data-products | Generates creation progress report of content for each tenant                                                                   |
| pythonscripts / [content\_creation\_status.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/etb/content\_creation\_status.py)                               | deprecated | Sunbird-Ed/sunbird-data-products | Generates content report based on status for each tenant                                                                        |
| pythonscripts / [content\_creation.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/etb/content\_creation.py)                                               | deprecated | Sunbird-Ed/sunbird-data-products | Generates creation progress report of content for each tenant                                                                   |
| pythonscripts / [etb\_metrics.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/etb/etb\_metrics.py)                                                         | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala                                                                                                   |
| pythonscripts / [consumption\_metrics.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/consumption\_metrics.py)                                 | deprecated | Sunbird-Ed/sunbird-data-products | Generates daily consumption report to respective tenant using druid data Deprecated since implemented through Hawkeye           |
| pythonscripts / [consumption\_metrics\_last\_30\_days.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/consumption\_metrics\_last\_30\_days.py) | deprecated | Sunbird-Ed/sunbird-data-products | Generates daily consumption report for last 30 days to respective tenant                                                        |
| pythonscripts / [consumption\_metrics\_v2.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/consumption\_metrics\_v2.py)                         | deprecated | Sunbird-Ed/sunbird-data-products | Generates daily consumption report to respective tenant using blob telemetry files.Deprecated since implemented through Hawkeye |
| pythonscripts / [gps\_learning.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/gps\_learning.py)                                               | deprecated | Sunbird-Ed/sunbird-data-products | Generates user’s consumption level on textbook as report for each state                                                         |
| pythonscripts / [report\_merger.py](https://github.com/Sunbird-Ed/sunbird-data-products/blob/release-4.10.5/python-scripts/src/main/python/dataproducts/services/consumption/report\_merger.py)                                             | deprecated | Sunbird-Ed/sunbird-data-products | Implemented the same in scala                                                                                                   |
| etl-jobs / learner / GroupsServiceTablesMigration                                                                                                                                                                                           | deprecated | Sunbird-Ed/sunbird-data-products | Script to migrate group related data to new tables                                                                              |
| etl-jobs / learner / UserLookupMigration                                                                                                                                                                                                    | deprecated | Sunbird-Ed/sunbird-data-products | Script to get users count based on users' information for analysis                                                              |

***

\[\[category.storage-team]] \[\[category.confluence]]