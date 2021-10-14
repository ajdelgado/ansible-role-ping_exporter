## Ansible role ping_exporter

Deploys [ping_exporter](https://github.com/ajdelgado/ping_exporter) script and install it as a systemd service unit.

# Configuration

Check [defaults](/defaults/main.yml) but create a dictionary *ping_exporter* with this values:
- prometheus_host: IP or hostname of prometheus host to open access in UFW (if specified)
- targets: List of IPs to ping
- log_file: Log file for debug information (A logrotate rule will be added to rotate it)
- count: Number of pings to send to each host
- port: Port for the web service to listen
- frequency: Delay between pings to each host
- interval: Time between packets sent
- timeout: The maximum waiting time for receiving a reply in seconds
- family: IP family version to use (A string "4" or "6")
- handle_ufw: Whether to create an "allow" rule in UFW for the port and the Prometheus server IP or hostname.