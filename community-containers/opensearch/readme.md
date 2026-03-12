## OpenSearch

This container bundles [OpenSearch](https://opensearch.org/) for you.

> **Find the meaning in your data**\
> OpenSearch is an open source, enterprise-grade search and observability suite that brings order to unstructured data at scale

### Activation

1. **Create a backup** of your AIO instance first.
2. In the AIO interface, scroll down to the **Community Containers** section.
3. Enable the **OpenSearch** checkbox and click **Save changes**.
4. Click **Stop containers**, then **Start and update containers**.

See https://github.com/nextcloud/all-in-one/tree/main/community-containers#community-containers for general instructions.

### Data Persistence and Backup

Index data is stored in the Docker volume `nextcloud_aio_opensearch` and is included in AIO backups automatically.

### Notes
- This container uses port 19200 (instead of default 9200), to be compatible with the [Elasticsearch](https://github.com/nextcloud/all-in-one/tree/main/Containers/fulltextsearch) container.

### Repository
https://github.com/opensearch-project/opensearch

### Maintainer
https://github.com/foertel







### Verification

Once the container is running, verify that OpenSearch is responding:

```bash
# From the host, via the Nextcloud container
docker exec nextcloud-aio-nextcloud curl -s http://nextcloud-aio-opensearch:9200

# Or check container logs
docker logs nextcloud-aio-opensearch
```

A successful response will be a JSON object containing the cluster name (`nextcloud-aio`), version info, and a `"tagline" : "The OpenSearch Project: https://opensearch.org/"` field.


### Removal

To remove this container, disable it in the AIO interface, then clean up:

```bash
sudo docker rm nextcloud-aio-opensearch
sudo docker image prune -a
sudo docker volume rm nextcloud_aio_opensearch
```

### Client Integration (Future)

The current official Nextcloud full-text search stack (`fulltextsearch` + `fulltextsearch_elasticsearch`) uses the Elasticsearch PHP client, which actively rejects connections to OpenSearch servers. A dedicated OpenSearch connector for Nextcloud is planned as a separate project. Once available, this container definition will be updated with `nextcloud_exec_commands` to auto-configure the integration.

### Repository
https://github.com/nextcloud/all-in-one/tree/main/community-containers/opensearch

### Maintainer
https://github.com/nextcloud
