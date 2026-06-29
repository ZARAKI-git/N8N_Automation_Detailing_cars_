# Detailing Colors — WhatsApp Booking Automation (n8n)

> An n8n workflow that turns inbound WhatsApp messages into booked car-detailing appointments — understood by Claude, logged to Google Sheets, and replied to automatically.

<p>
  <img alt="n8n" src="https://img.shields.io/badge/n8n-Workflow-EA4B71?logo=n8n&logoColor=white">
  <img alt="Anthropic" src="https://img.shields.io/badge/Anthropic-Claude-D97757?logo=anthropic&logoColor=white">
  <img alt="WhatsApp" src="https://img.shields.io/badge/WhatsApp-Cloud%20API-25D366?logo=whatsapp&logoColor=white">
  <img alt="Google Sheets" src="https://img.shields.io/badge/Google%20Sheets-Bookings-34A853?logo=googlesheets&logoColor=white">
</p>

## Overview

This repository contains an [n8n](https://n8n.io) automation that powers WhatsApp-based
booking for the **Detailing Colors** car studio. When a customer messages on WhatsApp, the
workflow uses Claude to interpret the request, applies booking logic, records the booking in
Google Sheets, and sends an automated reply back to the customer.

## How It Works

1. **Webhook trigger** — receives inbound WhatsApp messages (`detailing-colors-whatsapp`).
2. **Claude (Anthropic)** — parses the message to extract intent and booking details.
3. **Code + IF logic** — normalizes the data and branches based on the request.
4. **Google Sheets** — appends/updates the booking record.
5. **HTTP requests** — send the reply back via the WhatsApp Cloud API.

## Nodes Used

`Webhook` · `Anthropic (Claude)` · `Code` · `IF` · `Google Sheets` · `HTTP Request`

## Getting Started

### Prerequisites
- An [n8n](https://n8n.io) instance (self-hosted or cloud)
- A WhatsApp Cloud API (Meta) account and phone number
- An Anthropic API key
- A Google account with Sheets access

### Import the workflow

1. In n8n, go to **Workflows → Import from File**.
2. Select [`Detailing Colors - WhatsApp Booking Workflow.json`](./Detailing%20Colors%20-%20WhatsApp%20Booking%20Workflow.json).
3. Configure credentials for **Anthropic**, **Google Sheets**, and the **WhatsApp Cloud API**.
4. Point your WhatsApp webhook at the workflow's webhook URL.
5. Activate the workflow.

## Configuration Notes

- Replace any placeholder IDs/tokens (phone number ID, sheet ID, credentials) with your own.
- Test in n8n's editor with a sample payload before going live.

## License

Proprietary — all rights reserved.
