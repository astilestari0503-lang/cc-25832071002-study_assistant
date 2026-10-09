# Requirements

## Problem Statement
Penyebaran aplikasi web tradisional sering kali memerlukan konfigurasi manual yang rumit pada server publik, sehingga rentan terhadap kesalahan konfigurasi keamanan dan eksposur port backend yang tidak diinginkan. Proyek ini mendefinisikan standar deployment pertama yang aman menggunakan arsitektur reverse proxy lokal.

## Target Users
- Administrator Sistem / Cloud Engineer
- Pengembang Aplikasi Web Flask

## Functional Requirements
- FR-01 Aplikasi dapat melayani permintaan halaman web utama secara publik.
- FR-02 Aplikasi menyediakan endpoint kesehatan (`/health`) untuk pemantauan status sistem.

## Non-Functional Requirements
- NFR-01 Backend aplikasi hanya berjalan pada loopback lokal (`127.0.0.1:8000`).
- NFR-02 Manajemen proses aplikasi dikelola sepenuhnya oleh `systemd` agar berjalan otomatis di latar belakang.
- NFR-03 Permintaan publik diteruskan dengan aman melalui web server reverse proxy (Caddy).
- NFR-04 Repositori bersih dari informasi rahasia (*no secret in repository*).

## Constraints
- 1 vCPU
- 1 GB RAM
- 20 GB disk
- Ubuntu Server 24.04
- Public IPv4 (`4.197.24.35`)

## Acceptance Criteria M03
- [x] first deployment accessible
- [x] health endpoint works
