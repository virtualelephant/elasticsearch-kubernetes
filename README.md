# elasticsearch-kubernetes
Deployment files for Fluentd, Kibana and Elasticsearch on Kubernetes

- elasticsearch_pv.yaml: Creates the persistent volume for Elasticsearch via NFS
- elasticsearch_svc.yaml: Creates the headless service for Elasticsearch
- elasticsearch_statefulset.yaml: Creates the Elasticsearch StatefulSet
- kibana_pv.yaml: Creates the persistent volume for Kibana via NFS
- kivana_svc.yaml: Creates the service account for Kibana
- kibana_deployment.yaml: Creates the deployment for Kibana
- fluentd_rbac.yaml: Creates the RBAC cluster roles for Fluentd
- fluentd_daemonset.yaml: Creates the Fluentd DaemonSet to run on all nodes and masters

NOTES:
- If using NFS, make sure the export for Elasticsearch has the 'no_root_squash' option set.
- If using an external load balancer (like HAProxy), add a rule for the Kibana NodePort 30010.

INSTRUCTIONS:
Execute the following commands:

- kubectl create -f elasticsearch_pv.yaml
- kubectl create -f elasticsearch_svc.yaml
- kubectl create -f elasticsearch_statefulset.yaml

- kubectl create -f kibana_pv.yaml
- kubectl create -f kibana_svc.yaml
- kubectl create -f kibana_deployment.yaml

- kubectl create -f fluentd_rbac.yaml
- kubectl create -f fluentd_daemonset.yaml
