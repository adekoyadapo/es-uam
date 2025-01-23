# Elastic Stack UAM Guide

## **Intro**

This contains instructions on the full set of activities to complete the User Activity Monitoring Customer Architecture Play. The approach is broken into Kibana Auditing and Elasticsearch Auditing and documented in such a way that either or both can be delivered.

This guide assumes the following:
* A Platinum or Enterprise Subscription level (https://www.elastic.co/subscriptions) - see rows: Elasticsearch audit logging, Kibana audit logging
* Relevant permissions to access system indices in the cluster
* [Remote Cluster setup](https://www.elastic.co/guide/en/elasticsearch/reference/current/remote-clusters.html) for the main cluster(s) and the monitoring cluster
* [Stack monitoring setup](https://www.elastic.co/guide/en/kibana/current/xpack-monitoring.html)
* Audit logging enabled through filebeat and shipped to a monitoring cluster
  - [Kibana Audit logs](https://www.elastic.co/guide/en/kibana/current/xpack-security-audit-logging.html)
  - [Elasticsearch Audit logs](https://www.elastic.co/guide/en/elasticsearch/reference/current/enable-audit-logging.html)
  - Additional [filtering](https://www.elastic.co/guide/en/elasticsearch/reference/current/auditing-settings.html) to reduce log volume

## Deployment Overview
![Tech Spec Diagram](./archi-dagrams/UserActivityMonitoring_v3.png)


=======
The folder for ECK deployment mechanism contains a tailored README.md.

 ## **Folder Structure**

### Deployment mechanism: 

1. **[ECK](./eck/README.md) - standalone filebeat**

Contents:
- Assets to manually deploy Stack UAM / [Slowlogging](https://www.elastic.co/guide/en/elasticsearch/reference/current/index-modules-slowlog.html) in an on-premise environment.

2. **[assets](./assets/)**

Contents:
- Dashboard exports:
   - post8.14-dashboard.ndjdson (Full Stack UAM dashboard collection compatible with versions > 8.14 )
   - slowlog.ndjson (Slowlog-only dashboard)
