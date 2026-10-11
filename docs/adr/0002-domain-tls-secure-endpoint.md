# ADR-0002: Public DNS and TLS Termination with Caddy

## Status
Accepted

## Context

M03 menggunakan public IPv4 dan HTTP.
M04 membutuhkan hostname stabil dan secure endpoint.
VPS memiliki 1 vCPU, 1 GB RAM, Ubuntu Server 24.04.

## Decision

- gunakan subdomain publik;
- gunakan A record ke public IPv4 VPS;
- jangan membuat AAAA tanpa IPv6 yang valid;
- gunakan Caddy sebagai TLS terminator dan reverse proxy;
- pertahankan Gunicorn pada 127.0.0.1:8000;
- buka TCP/80 dan TCP/443;
- gunakan automatic HTTPS Caddy.

## Alternatives Considered

1. NGINX + Certbot
2. Apache + Certbot
3. aplikasi melayani TLS langsung
4. self-signed certificate
5. akses berbasis IP tanpa domain

## Rationale

Jelaskan alasan berdasarkan:
- footprint VPS;
- automation;
- maintainability;
- separation of concerns;
- learning outcomes.

## Consequences

### Positive
- valid public HTTPS;
- certificate lifecycle otomatis;
- aplikasi tetap sederhana;
- backend tidak diekspos.

### Negative
- dependency pada DNS yang benar;
- dependency pada CA/ACME availability;
- port 80/443 harus reachable untuk challenge default.

## Risks

- DNS salah;
- AAAA stale;
- provider firewall menutup 80/443;
- certificate issuance rate limit jika eksperimen berulang tidak terkontrol.

## Review Trigger

Tinjau jika:
- pindah provider;
- menambah load balancer/CDN;
- mengadopsi container/orchestrator;
- membutuhkan wildcard certificate.
