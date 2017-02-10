# Docker compose - Monitoring

This docker compose file describes the monitoring stack for NTU HPC team.

## Usage

To run the containers, do

```bash
$ docker-compose up -d
```

This exposes ports `8086` and `2003` for InfluxDB, and port `3000` for Grafana.
The configuration file `influxdb.conf` is loaded into the InfluxDB container.