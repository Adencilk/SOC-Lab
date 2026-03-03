# Troubleshooting – SOC Lab

## Service Failures
- Wazuh Manager timeouts: resolved by removing `/var/ossec/var/start-script-lock`
- Indexer startup failures: checked logs, removed stale indexer lock

## Resource Issues
- VM memory limitations caused service failures
- Adjusted RAM and CPU for each VM to ensure stable operation

## Permissions
- Linux agents required sudo privileges for commands
- Resolved “permission denied” errors when listing or editing files

## Alerts & Logs
- Verified agent connectivity
- Checked Wazuh dashboard for real-time logs
- Simulated attacks to confirm alert generation
