---
icon: elementor
---

# Cloud URL variabilisation instead of using CNAME

## Introduction <a href="#introduction" id="introduction"></a>

In Sunbird Lern, there are few cases where blob url is stored in DB and ES.

1. Old certificates are stored in cloud storage. Whenever user tries to download any specific certificate, cert-service is generating the signed URL and sending the response back to the portal with the downloaded data by using this signed URL. Below is the sample signed URL:

[Signed URL](https://preproddp.blob.core.windows.net/preprod-e-credentials/01351412976428646422/1d8e0eae-1bfa-4446-ad60-4ede07112eea.json?sv=2017-04-17\&se=2022-10-18T18%3A10%3A02Z\&sr=b\&sp=r\&sig=MJXHVv6tm%2B1TueIyNO2s2cjN6Cw7D/lUvMghpXGDkzE%3D)

`https://preproddp.blob.core.windows.net/preprod-e-credentials/01351412976428646422/1d8e0eae-1bfa-4446-ad60-4ede07112eea.json?sv=2017-04-17&se=2022-10-18T18%3A10%3A02Z&sr=b&sp=r&sig=MJXHVv6tm%2B1TueIyNO2s2cjN6Cw7D/lUvMghpXGDkzE%3D`

2\. Certificate Template urls are stored in Course\_batch table (cassandra), Training certificate table(postgres) and course batch ES index and RC ES. These template urls are uploaded by asset apis in knowledge, so asset apis return the urls.

3\. Exhaust reports are uploaded and blob url is stored in job\_request table in postgres - analytics DB

4\. Userorg file upload api, uploads files to cloud

## Problem Statement <a href="#problem-statement" id="problem-statement"></a>

Whenever there is change with respect to the Cloud Service Providers we have to write migration scripts to update all the relevant tables with the new cloud service provider URL. For this cname can be used , but if there are any domain name changes w.r.t cname, then again migration scripts have to be run. Configuring cname url and using that variable while storing blob urls to DB or ES is a good approach. Thi will help to avoid the need to run the migration scripts whenever there are changes to the cloud service providers.

## Design <a href="#design" id="design"></a>

In order to achieve this goal we can have the CNAME as configurable value, so that any service provider dealing with the cloud storage service providers have to resolve this configured value.

For example:

`CNAME:https://preproddp.blob.core.windows.net/preprod-e-credentials/01351412976428646422/1d8e0eae-1bfa-4446-ad60-4ede07112eea.json Proposed URL: $CLOUD_STORE_BASE_PATH/preprod-e-credentials/01351412976428646422/1d8e0eae-1bfa-4446-ad60-4ede07112eea.json`

All the services which are using the CNAME record as of now has to be modified so that the `$CLOUD_STORE_BASE_PATH` will be replaced in the URL with the configured variable value.

Below mentioned services may require changes under Sunbird Lern:

User Org Service (sunbird-lms-service)Batch Service (sunbird-learner-service)

Below mentioned services may require changes under Sunbird Lern:

User Org Service (sunbird-lms-service)

In User Org Service while uploading the file to the cloud we are making use the cloud-sdk and sending the provided actual URL in the response. - No change is needed here as we are sending actual URL in the response.

Batch Service (sunbird-learner-service)

In Batch Service changes have to be made with the changes by resolving the configured name.

1. Bulk batch enrolment upload - signed url generation .
2. Textbook upload and download - No changes, uri is created from id in code itself.
3. QRcode Image download api downloads the QRcode from dialcode.dialcode\_image table.
   1. csv contains qrcode imageblob urls, this need to be resolved before downloading. csp base path variable should be replaced with the csp url. Also the csv is uploaded and its blob url is shared. That should be actual url in response.
4. All certificate templates in batch table and Training Certificate table
   1. Cert template url is stored in both tables and needs to be saved with the configured name and needs to be resolved in each get/read/search service calls. Using play filter is ok for resolving response, but for request it may not be possible if we want to store separate values in DB and ES.
   2. If we get **cname url/actual url** (cert template url) in request, we need to convert this in to `$CLOUD_STORE_BASE_PATH` before storing in course batch table in DB. Should we save the `$CLOUD_STORE_BASE_PATH` into RC during certificate generation or the actual path?
   3. If certificate object stored in RC will have the $CLOUD\_STORE\_BASE\_PATH then portal and app after fetching the template url from RC certificate obj, need to resolve the $CLOUD\_STORE\_BASE\_PATH to download certificate.
5. For old certificate download
   1. No certificate url is stored in DB
   2. Signed URL is being generated by the cloud-sdk and cloud sdk should check whether gcp or not and return the signed url.
6. Below APIs in sunbird-course-service(lms) have to be modified and the `$CLOUD_STORE_BASE_PATH` value has to be resolved

* sunbird-course-service(lms) - (`/v1/user/courses/list/`, `/v2/user/courses/list`, `/v2/user/courses/admin/list`, `/v1/course/batch/read/`)
* `For these APIs we have to replace actual URL with $CLOUD_STORE_BASE_PATH(/v1/course/batch/cert/template/add`, `/v1/course/batch/cert/template/remove`, `/v1/course/batch/create`, `/v1/course/batch/update`)

Migration Scripts

In the migration scripts use `$CLOUD_STORE_BASE_PATH` in the URLs instead of using the cname/direct URL for all the existing records in all the tables

Data Product Changes

In Data Products, Exhaust reports are stored with cloud url in job request table.

[https://sunbirdstagingprivate.blob.core.windows.net/reports/userinfo-exhaust/7B7463609693ABBB33F48\[…\]13BDE/0134278409923379202\_userinfo\_20211210.zip](https://project-sunbird.atlassian.net/wiki/spaces/UM/pages/3250388997/Cloud+URL+variabilisation+instead+of+using+CNAME)

* This url is returned by analytics\_core in Sunbird Obsrv , so will analytics core return cname url or cname\_variable url? - it will return full csp specific url
* Exhaust job should filter out the relative path and store in job\_request table
* ReportService API in Sunbird Obsrv should read the `relative path` and genrate signed url.

Other reports should work fine without any issues.

## Conclusion <a href="#conclusion" id="conclusion"></a>

Instead of running migration scripts for all the records whenever there is any change to the Cloud Service Provider we can use the configured variable name as one time activity.
