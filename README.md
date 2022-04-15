# Set up 3-nodes Elasticsearch by docker-compose

> Read more: https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html

### Start your cluster with security enabled and configured
1. Modify the `.env` file and enter strong password values for both the `ELASTIC_PASSWORD` and `KIBANA_PASSWORD` variables.

    > You must use the `ELASTIC_PASSWORD` value for further interactions with the cluster. The `KIBANA_PASSWORD` value is only used internally when configuring Kibana.

2. Create and start the three-node Elasticsearch cluster and Kibana instance:

    ```bash
    docker-compose up -d
    ```

3. When the deployment has started, open a browser and navigate to http://localhost:5601 to access Kibana, where you can load sample data and interact with your cluster.

### Stop and remove the deployment
To stop the cluster, run docker-compose down. The data in the Docker volumes is preserved and loaded when you restart the cluster with docker-compose up.
```bash
docker-compose down
```

To delete the network, containers, and volumes when you stop the cluster, specify the `-v` option:
```bash
docker-compose down -v
```
