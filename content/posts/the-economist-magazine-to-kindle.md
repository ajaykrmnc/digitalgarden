---
title: "TheEconomist Magazine to Kindle"
date: 2025-01-08
categories: ["Coding", "Productivity"]
tags: ["kindle", "automation", "bash", "epub"]
description: "Automating The Economist magazine delivery to Kindle using Monkfishare repo and calibre-smtp"
draft: false
---

## The Goal

Get The Economist magazine delivered to my Kindle automatically every week, without manual intervention.

## The Solution: Monkfishare Repository

I discovered the [Monkfishare](https://github.com/monkfishare) repository which provides tools for downloading and converting The Economist to Kindle-compatible formats.

## Automation Script

Here's the bash script that automates the entire process:

```bash
#!/bin/bash

# The Economist to Kindle Automation Script
# Uses Monkfishare repo and calibre-smtp for delivery

set -e

# Configuration
DOWNLOAD_DIR="$HOME/economist-downloads"
KINDLE_EMAIL="your-kindle@kindle.com"
SMTP_SERVER="smtp.gmail.com"
SMTP_PORT="587"
SENDER_EMAIL="your-email@gmail.com"

# Create download directory
mkdir -p "$DOWNLOAD_DIR"
cd "$DOWNLOAD_DIR"

# Download latest issue (using monkfishare tools)
echo "Downloading latest issue..."
# Clone or update the repo
if [ -d "economist-downloader" ]; then
    cd economist-downloader && git pull
else
    git clone https://github.com/monkfishare/economist-downloader.git
    cd economist-downloader
fi

# Run the download script
python3 download.py --output "$DOWNLOAD_DIR/economist.epub"

# Convert to MOBI if needed (Kindle prefers MOBI/AZW3)
echo "Converting to Kindle format..."
ebook-convert "$DOWNLOAD_DIR/economist.epub" "$DOWNLOAD_DIR/economist.mobi"

# Send to Kindle using calibre-smtp
echo "Sending to Kindle..."
calibre-smtp \
    --relay "$SMTP_SERVER" \
    --port "$SMTP_PORT" \
    --username "$SENDER_EMAIL" \
    --password "$SMTP_PASSWORD" \
    --encryption-method TLS \
    --subject "The Economist - $(date +%Y-%m-%d)" \
    "$SENDER_EMAIL" \
    "$KINDLE_EMAIL" \
    "Weekly Economist delivery" \
    --attachment "$DOWNLOAD_DIR/economist.mobi"

echo "✅ The Economist sent to Kindle successfully!"

# Cleanup old files (keep last 4 issues)
find "$DOWNLOAD_DIR" -name "*.mobi" -mtime +28 -delete
find "$DOWNLOAD_DIR" -name "*.epub" -mtime +28 -delete
```

## Setting Up the Cron Job

Schedule weekly delivery (every Saturday at 8 AM):

```bash
# Edit crontab
crontab -e

# Add this line
0 8 * * 6 /path/to/economist-to-kindle.sh >> /var/log/economist-kindle.log 2>&1
```

## Prerequisites

1. **Calibre**: Install for `ebook-convert` and `calibre-smtp`
   ```bash
   brew install calibre  # macOS
   ```

2. **Kindle Email**: Add your sender email to approved list in Amazon settings

3. **App Password**: Generate an app-specific password for Gmail

## Result

Every Saturday morning, The Economist lands on my Kindle, ready for weekend reading. No manual steps, no browser visits, just quality journalism delivered automatically.

