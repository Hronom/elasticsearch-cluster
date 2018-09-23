# Prerequisite
Docker [how-to install](https://docs.docker.com/engine/installation/)  
Docker Compose [how-to install](https://docs.docker.com/compose/install/)

# Run using Docker Compose
### Run
```
docker-compose up -f elasticsearch-cluster-x -d --remove-orphans
```

### Down
```
docker-compose -f elasticsearch-cluster-x down -v
```

# URL's
Cluster state: `http://localhost:9200/_cluster/state?pretty`  
Kibana: `http://localhost:5601/app/kibana`  
elasticsearch-head: `http://localhost:9100/`

# Deploy in AWS `t2.medium`
Set `Virtual memory` like described here [https://www.elastic.co/guide/en/elasticsearch/reference/5.6/vm-max-map-count.html](https://www.elastic.co/guide/en/elasticsearch/reference/5.6/vm-max-map-count.html)
```
sudo sysctl -w vm.max_map_count=262144
```

Copy `docker-compose.yml` file in that instance.  

In the directory with this file execute command:
```
sudo docker-compose -f elasticsearch-cluster-x up -d
```

Then you can try links described below to access cluster.