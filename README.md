# security-projects

A collection of Python scripts, SIEM detection rules, Splunk configs, threat hunting queries, and incident response work built across various homelab projects.

## Scripts

### T-POT Threat Intelligence Pipeline

Scripts from the [T-POT Honeypot Threat Intelligence](https://github.com/TrystanRuiz/tpot-honeypot-threat-intel) project. Pulls attacker IPs from T-POT's Elasticsearch, scores them against AbuseIPDB, and pushes high-risk IPs to OPNsense as a firewall blocklist via REST API.

- **[ip_reputation_check.py](scripts/ip_reputation_check.py)** - Sync version. Checks IPs one at a time, baseline for benchmarking.
- **[ip_reputation_check_async.py](scripts/ip_reputation_check_async.py)** - Async version using asyncio and aiohttp. Fires up to 10 concurrent AbuseIPDB requests, 76% faster than sync (34s to 8s on 90 IPs).
