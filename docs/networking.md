# Networking — M04

## VPS

Public IPv4: `<REDACT_OR_VALUE_AS_POLICY>`

## Interface

Main interface: ...

## Default Route

...

## DNS

Domain: `<DOMAIN>`
Record: A → `<PUBLIC_IPV4>`
AAAA: not configured unless verified IPv6 exists

## Public Ports

| Port | Protocol | Purpose |
|---:|---|---|
| 22 | TCP | SSH administration |
| 80 | TCP | HTTP redirect / ACME HTTP-01 |
| 443 | TCP | HTTPS |

## Internal Ports

| Address | Port | Service |
|---|---:|---|
| 127.0.0.1 | 8000 | Gunicorn |

## Firewalls

- provider firewall
- UFW

## Validation Commands

...
