---
icon: elementor
---

# Load-balancer-Configurations

**Load balancer:**

You can scale your applications and create high availability for your services.It provides

low latency and high throughput,and scales up to millions of flows for all TCP and UDP applications.

Load Balancer distributes new inbound flows that arrive on the Load Balancer's frontend to backend pool

instances, according to rules and health probes.

**Agent-swarm:**

Frontend ip configuration - attach public ip

Backend pools - attach agent vm's or availability set of agent group

Health Probes/check - Configure path and port - 80 and 443 (both)

EX: name: http

protocol: TCP

port: 80

interval: 5

unhealthy threshold: 2

Load Balancing rules - Frontend-ip-config,Frontend-port,backend-port, Backend-pool and health-probe

Ex: Frontend-port: 80

backend-port: 80

Similarly steps for port 443

**Keycloak-swarm:**

Frontend ip configuration - Internal ip by default

Backend pools - attach keycloak vm or availability set of keycloak group

Health Probes/check - Configure path and port - 8080

EX: name: keycloakhealth

protocol: TCP

port: 8080

interval: 5

unhealthy threshold: 2

Load Balancing rules - Frontend-ip-config,Frontend-port, backend-port, Backend-pool and health-probe

Ex: Frontend-port: 80

backend-port: 8080

**KP-LB Services:**

Frontend ip configuration - Internal ip by default

Backend pools - attach vm's of learning and search or availability set for learning and search

Health Probes/check - Configure path and port - 8080 (for learning) and 9000 (for search)

EX: name: learninghealth

protocol: http

port: 8080

path: /learning-service/health

interval: 5

unhealthy threshold: 2

Frontend-port: 8080

backend-port: 8080

name: searchhealth

protocol: http

port: 9000

path: /health

interval: 5

unhealthy threshold: 2

Load Balancing rules - Frontend-ip-config,Frontend-port, backend-port, Backend-pool and health-probe

Ex: Frontend-port: 9000

backend-port: 9000

**DP-LB Services: (analytic-api)**

Frontend ip configuration - Internal ip by default

Backend pools - attach vm's of analytics-api or availability set for analytics-api group

Health Probes/check - Configure path and port - 9000

EX: name: analyticshealth

protocol: tcp

port: 9000

interval: 5

unhealthy threshold: 2

Load Balancing rules - Frontend-ip-config,Frontend-port, backend-port, Backend-pool and health-probe

Ex: Frontend-port: 9000

backend-port: 9000

***

\[\[category.storage-team]] \[\[category.confluence]]
