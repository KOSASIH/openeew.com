---
id: create-dashboard
title: Create a monitoring dashboard
sidebar_label: Create dashboard
---

# OpenEEW Dashboard

## Grafana
[Grafana](https://github.com/grafana/grafana) provides a low-latency visualization of time-series data. Perfect for real-time accelerations from OpenEEW sensors!

### Install
(note: see [issue](https://github.com/openeew/openeew-detection/issues/46) for adding Grafana to OpenEEW docker)
Once Grafana is [installed](https://grafana.com/docs/grafana/latest/installation/), either through Docker or manually, you can connect the time-series database and create a new dashboard.

### Add data source
You should add the two postgres tables as unique data sources for Grafana; add the `devices` table, and add the `eew` table. You can view the schema [here](https://github.com/openeew/openeew-detection/blob/master/init_db.sql).

### Create dashboard
You can see examples of dashboards [here](https://github.com/openeew/openeew-dashboard/tree/master/grafana/dashboard). These can be imported directly into Grafana.

For example, the `sensor location.json` creates a dashboard which shows sensor positions and status:
![OpenEEW sensor locations dashboard](images/sensor-location.png?raw=true "sensor locations dashboard")

In another example, `sensor traces.json` you can view live streaming accelerations from your sensors:
![OpenEEW sensor locations dashboard](images/traces-stream3.gif?raw=true "sensor traces dashboard")


## Custom Dashboard
It is planned to create a custom dashboard that allows for the following:
- Automated user authentication through OAuth2 or similar
- Ability to connect to your sensor device, or the global OpenEEW network of devices
- Ability to configure your device (sample rate, device ID) and also query statistics (connectivity, signal quality)
- Ability to see historic data from your device and run simulations with detection system
- Ability to visualize sensor accelerations for each axis
- Ability to see sensor on map (for example OpenStreetMap).
