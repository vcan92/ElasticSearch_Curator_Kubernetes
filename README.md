# Elastic Search Curator Kubernetes Deployment

# You can deploy ElasticSearch Curator and Crontab on your kubernetes environment with this repository. This repository delete your Elastic Search indices older than 30 days.(based on index name).
## About Elastic Search Curator

Elasticsearch Curator helps you curate, or manage, your Elasticsearch indices and snapshots by:
*  Obtaining the full list of indices (or snapshots) from the cluster, as the actionable list
* Iterate through a list of user-defined filters to progressively remove indices (or snapshots) from this actionable list as needed.
* Perform various actions on the items which remain in the actionable list.

More Information [Curator](https://www.elastic.co/guide/en/elasticsearch/client/curator/current/about.html#about)

## About Crontab

crontab is a UNIX command that creates a table or list of commands, each of which is to be executed by the operating system at a specified time. crontab is used to create the crontab file (the list) and later used to change the previously created crontab file.

### Prerequisites

* Docker
* Kubernetes

### Installation

```sh
$ change /etc/curator/curator.yml file (Replace your Elastic Search host)
$ change /etc/cron.d/curator file (you can create your own cron)
$ docker build (with your own tag) 
$ docker push (public or private repository)
$ change your deployment.yml file (Replace your image)
$ kubectl create -f namespace.yml
$ kubectl create -f deployment.yml -n elasticsearch-curator
```
