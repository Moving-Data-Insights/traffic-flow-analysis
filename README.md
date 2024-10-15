To use SQL in notebook: https://github.com/ploomber/jupysql

## Instructions
- Using MobilityDB docker to run the database.
- Using Grafana container for visualization.

### Connect the containered services
You need to connect the services in container for them to communicate with each other.

```bash
docker network create my-network
docker network connect my-network <grafana-container-name>
docker network connect my-network <postgres-container-name>
```
