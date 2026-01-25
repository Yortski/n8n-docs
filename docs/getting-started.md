# Getting Started with n8n

This guide helps you get n8n running quickly.

## Requirements
- Docker (recommended)
- OR Node.js 18+

## Install using Docker

```bash
docker volume create n8n_data

docker run -it --rm \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  n8nio/n8n
```