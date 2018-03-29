# Docker-compose files for a simple uptodate
# InfluxDB
# Grafana stack

## Security notes
The admin user is created the first time the application is run. The password
will not be updated in subsequent starts, regardless of what is set in the
environment variables (secrets.grafana/influxdb). Either change them manually or
delete the docker volume and all the associated data with
`docker volume rm *hash*` or `docker volume prune`. Deleting the volumes
requires the docker instances to be stopped.

Get the stack (only once):

```
git clone https://github.com/nicolargo/docker-influxdb-grafana.git
cd docker-influxdb-grafana
docker pull grafana/grafana
docker pull influxdb
```

Run your stack:

```
docker-compose up -d

```

Show me the logs:

```
docker-compose logs
```

Stop it:

```
docker-compose stop
docker-compose rm
```

Update it:

```
git pull
docker pull grafana/grafana
docker pull influxdb
```
