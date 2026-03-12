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

### Repository
https://github.com/opensearch-project/opensearch

### Maintainer
https://github.com/foertel