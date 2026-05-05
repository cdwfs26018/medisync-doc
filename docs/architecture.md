# MediSync — Architecture Documentation

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React |
| Backend | Laravel (REST API) |
| Database | MySQL |
| Hosting | VPS OVH |

## Overview

MediSync is a web application that allows general practitioners and specialists
to share prescriptions, medical reports and schedules in real time.

## Architecture

[React Frontend]
|
| HTTP/HTTPS
v
[Laravel REST API]
|
v
[MySQL Database]
All layers hosted on OVH VPS

## Infrastructure

- **Hosting:** OVH VPS
- **Backups:** Currently manual and irregular (to be automated)
- **Version control:** GitHub (direct push on main — to be improved)
- **CI/CD:** None currently in place

## Security & Compliance

- Medical data handled (special RGPD category)
- RTO target: 4 hours
- RPO target: 24 hours