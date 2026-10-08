# HouseFi

**Live:** [housefi.lovable.app](https://housefi.lovable.app) · **Code:** private

A full-stack platform for household bills and shared expenses, designed for roommates and shared apartments to track living costs transparently.

<!-- To add a screenshot: upload it to assets/housefi.png and put ![Screenshot](../assets/housefi.png) here -->

## What it does

- **House bills & fixed expenses:** track monthly and recurring utilities (rent, electricity, gas, internet, condo fees) with due dates, payment status and billing periods, plus a calendar and filterable history of upcoming and past payments.
- **Daily expense splitting (Splitwise-style):** day-to-day shared expenses are kept separate from core house bills. It records who paid and each roommate's share, lets people mark "I paid my share", and calculates net balances and settlements in real time.
- **AI receipt scanning (OCR):** upload a PDF or photo of a receipt or invoice, and AI extracts the vendor, amount, date and category to pre-fill a new bill.
- **Multi-user households:** invite roommates with an invite code, with admin/member roles, a real-time database protected by row-level security, and an audit trail of who added or changed bills and receipts.
- **AI assistant integration (MCP):** a built-in, OAuth-secured [Model Context Protocol](https://modelcontextprotocol.io) endpoint lets external AI agents check balances, log bills or settle expenses on a user's behalf.
- **Privacy & compliance:** GDPR-compliant data export and account deletion, with privacy, terms and cookie policies.

## Highlights

- Two AI integrations: document understanding (receipt OCR) and an MCP server that makes the app usable by AI agents.
- Multi-tenant data model: each household's data is isolated with row-level security and roles.
- Real-time balances and settlements across roommates.

## Stack

Full-stack web app · real-time Postgres database with row-level security · OAuth · AI OCR · Model Context Protocol (MCP) · built with Lovable
