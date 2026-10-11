## Production-like Development Endpoint
URL: `https://25832071002.4.197.24.35.sslip.io/`
Health: `https://25832071002.4.197.24.35.sslip.io/health`

## Network Architecture
Public entry points:
- TCP/80 → Caddy redirect/ACME
- TCP/443 → Caddy HTTPS

Internal application:
- `127.0.0.1:8000` → Gunicorn

## DNS
`25832071002.4.197.24.35.sslip.io` resolves through an A record to the VPS public IPv4.

## Security
- SSH public key authentication
- UFW
- loopback-only backend
- Caddy automatic HTTPS
