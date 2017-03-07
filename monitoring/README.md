# Docker compose - Monitoring

This docker compose file describes the monitoring stack for NTU HPC team.

## Usage

To run the containers, do

```bash
$ GFU=<grafana-user> GFP=<grafana-passwd> docker-compose up -d
```

The defaults in docker compose file has the following effects:

- Starts containers for `influxdb` and `grafana`
- Maps port `2003` of `influxdb` for listening on carbon input
- Maps port `3000` of `grafana` (to localhost)
- Mounts a volume to `influxdb` (at `/var/lib/influxdb`) and `grafana` (at `/var/lib/grafana`)
- Run `influxdb` according to `influxdb.conf`
- Sets `grafana` admin username according to `GFU` and password according to `GFP`
- Sets `grafana` root URL to be `grafana.ntuhpc.org`
- Disables user signup for `grafana`
- Enables anonymous user for organization `NTU HPC`

To add InfluxDB as a data source in Grafana, use the URL `http://influxdb:8086`.
