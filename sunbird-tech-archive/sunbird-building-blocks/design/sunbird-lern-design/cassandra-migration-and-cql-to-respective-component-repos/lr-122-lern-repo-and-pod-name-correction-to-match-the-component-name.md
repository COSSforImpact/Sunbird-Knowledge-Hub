---
icon: elementor
---

# LR-122--Lern-repo-and-pod-name-correction-to-match-the-component-name

## Introduction

Currently all the component names, repo names, pod names, and service names are not in sync with respect to naming.

[LR-122 System JIRA](https://browse/LR-122)

## Background & Problem Statement

Adopters are confused because the names are not in sync. e.g., currently sunbird-lms-service is the repo name for the UserOrg component, but lms-service is the service name for the Batch service component.

#### Key Design Problems

* Names are not is sync for component, repo, pods and service.

## Design

Aligning or suggesting the names based on the features they have, the table below has details about existing names and suggested names for the required ones.

| **Component Name**                                    | **Repo Name**                                                             | **Telemetry Data**                                                                                                                                                                                               | **JAR Name**                                                                                                               | **K8s Deploy Name**                           | **Service Name**                                                      | **Features**           |
| ----------------------------------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------- | ---------------------- |
| UserOrg **Suggested:** User Management ServiceUserOrg | sunbird-lms-service **Suggested:** user-management-serviceuserorg-service | pdata.id=.sunbird.learning.servicepdata.pid=learner-service **Suggested:** pdata.id=.sunbird.user.management.servicepdata.pid=user-management-servicepdata.id=.sunbird.user.org.servicepdata.pid=userorg-service | learning-service-1.0-SNAPSHOT.jar **Suggested** : user-management-service-1.0-SNAPSHOT.jaruserorg-service-1.0-SNAPSHOT.jar | learner **Suggested:** user-managementuserorg | learner-service **Suggested:** user-management-serviceuserorg-service | <ul><li>User</li></ul> |

* Org
* Location
* SystemSettings

\| | Batch Service \*\*Suggested:\*\* LMS Service | sunbird-course-service \*\*Suggested:\*\* lms-service | pdata.id=.sunbird.learning.servicepdata.pid=lms-service \*\*Suggested:\*\* pdata.id=.sunbird.lms.service | lms-service-1.0-SNAPSHOT.jar | lms | lms-service |

* Batch
* Certificate Template
* QR code download

\| | Group Service | groups-service | telemetry\_pdata\_id=dev.sunbird.groups.service telemetry\_pdata\_pid=groups-service | group-service-1.0.0.jar | groups | groups-service |

* Groups

\| | Notification Service | sunbird-notification-service \*\*Suggested:\*\* notification-service | telemetry\_pdata\_id=dev.sunbird.notifications.service telemetry\_pdata\_pid=notification-service | notification-service-1.0.0.jar | notification | notification-service |

* Notification

|

**Notes:**

* After renaming the service name, if any service is calling directly using the service url (e.g., [http://learner-service:9000](http://learner-service:9000) needs to be updated with [http://userorg-service:9000](http://userorg-service:9000)), then that service needs to change in its config/code.
* There will be no change in kong-api endpoints.

***

\[\[category.storage-team]] \[\[category.confluence]]
