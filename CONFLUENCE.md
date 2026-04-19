# CONNECT 2026 - Email Sender Tool

**Quick Reference** | [Full Documentation on GitHub](https://github.com/Tomcohen514/connect2026)

## Overview

Internal operations tool for sending emails to event attendee groups using Kaltura's messaging system. Generates cURL commands that ops teams can run in Terminal or Postman.

## What It Does

- Authenticates with Kaltura credentials (generates KS and JWT tokens)
- Lists available events from EPM
- Loads email templates and attendee groups for selected event
- Generates ready-to-run cURL commands for sending emails

## Quick Start

1. Upload [email-sender.html](https://github.com/Tomcohen514/connect2026/blob/main/email-sender.html) to any web server
2. Open in browser (requires FortiClient VPN for internal API access)
3. Login with Partner ID, email, and password
4. Select event, template, and target groups
5. Click "Generate Command"
6. Copy and run cURL command in Terminal or Postman

## Files

- **email-sender.html** - Standalone HTML tool (no backend needed)
- **send-email-proxy.php** - Optional CORS proxy for browser-based sending
- **README.md** - Complete documentation with sequence diagram

## Technical Flow

The tool performs these steps:

1. **Authentication** - Login → Generate KS token → Convert to JWT
2. **Event Selection** - Fetch events list → User selects event
3. **Data Loading** - Fetch App GUID, email templates, and groups
4. **Command Generation** - Build messaging API payload with selected options
5. **Manual Execution** - User runs cURL in Terminal (bypasses CORS issue)

## Why cURL Commands?

The Kaltura Messaging API doesn't support CORS for browser requests. The tool generates cURL commands instead of sending directly from the browser. This approach:

- Works around CORS restrictions
- Gives ops teams full visibility into the API call
- Allows validation before sending

## Links

- **GitHub Repository:** https://github.com/Tomcohen514/connect2026
- **Full Documentation:** [README.md](https://github.com/Tomcohen514/connect2026/blob/main/README.md)
- **Download Tool:** [email-sender.html](https://github.com/Tomcohen514/connect2026/blob/main/email-sender.html)

## Security Notes

- Never commit credentials to version control
- KS tokens expire after 24 hours
- Use placeholders (YOUR_PARTNER_ID) when sharing examples

---

**Maintained by:** Solutions Team  
**Last Updated:** April 2026  
**Status:** Production-ready
