# Agent.wp — Headless WordPress CPT & Docker Setup

Backend Headless WordPress repository for **NEXUS.DEALS** multi-store broker hub.

## Overview

This repository contains the custom WordPress configuration, custom post types (CPT), plugins, and Docker setup for serving product deals via the WordPress REST API to the Astro frontend (`the-agent.xyz`).

## File Structure

```
├── wp-content/
│   └── mu-plugins/
│       └── nexus-products.php   # Custom CPT 'product' with REST API meta fields
├── mysql-init/                  # MySQL database initialization scripts
├── docker-compose.yml           # WordPress + MySQL Docker stack
└── README.md
```

## Setup Instructions

1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```

2. Start the WordPress stack with Docker:
   ```bash
   docker-compose up -d
   ```

3. Access WordPress Admin:
   - URL: `http://localhost:8000/wp-admin`
   - REST API Endpoint: `http://localhost:8000/wp-json/wp/v2/product`

## Custom Post Type (`product`)

The plugin `nexus-products.php` registers the `product` CPT with `show_in_rest = true` and `price` meta field support.
