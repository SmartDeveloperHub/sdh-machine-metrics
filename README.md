# SDH-Machine-Metrics

Docker deployment of Metrics Micro Services.

This repository deploys these containers:
* Redis Database for Metrics
* Qualitative Service
* Source Code Management Service
* Organization Service
* Continuous Integration Service
* Nginx

### Ports (container - host):
* SCM: 5003 - 5003
* ORG: 5004 - 5004
* CI: 5005 - 5005
* QI: 5006 - 5006
* Nginx: 80 - 9004

### Nginx Access:
|Nginx Path|Container/Path|
|:---------|:----------|
|/qualitative/api|qmetrics/api|
|/qualitative/metrics|qmetrics/metrics|
|/qualitative/views|qmetrics/views|
|/scm/api|scmmetrics/api|
|/scm/metrics|scmmetrics/metrics|
|/scm/views|scmmetrics/views|
|/ci/api|cimetrics/api|
|/ci/metrics|cimetrics/metrics|
|/ci/views|cimetrics/views|
|/org/api|orgmetrics/api|
|/org/metrics|orgmetrics/metrics|
|/org/views|orgmetrics/views|

### Docker - Requirements:

* docker > 1.7.0
* docker-compose > 1.3.1

### Docker - Usage:

|Alias|Command|
|:---------|:----------|
|Start|```docker-compose up -d```|
|Stop|```docker-compose stop```|
|Delete|```docker-compose rm -f```|
|Rebuild|```docker-compose build```|

### Docker - Tips:

If you want to change port redirection or configuration, we suggest you:

1. Stop
2. Delete
3. Build (if you have changed any file or physical configuration)
4. Start

### Metrics - Usage:

Before deployment, you need to edit docker-compose.yml.

Put AGORA_HOST and BROKER_HOST value.
