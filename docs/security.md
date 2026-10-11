# Security Baseline — M04

## Identity and Administration

- non-root SSH user
- public key authentication
- password SSH disabled

## Network Exposure

Public:
- 22/tcp
- 80/tcp
- 443/tcp

Private to host:
- 127.0.0.1:8000

## Transport Security

- public HTTPS
- certificate managed by Caddy
- HTTP redirects to HTTPS

## HTTP Response Headers

- X-Content-Type-Options
- Referrer-Policy
- X-Frame-Options

## Known Limitations

- single VPS
- no WAF
- no application authentication yet
- no centralized log system
- no external uptime monitoring yet
