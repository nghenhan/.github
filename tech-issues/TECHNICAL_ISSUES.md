# Technical Issues Report

## Overview
This document tracks ongoing technical issues and their resolutions. It is updated as new issues are discovered and existing ones are resolved.

### Proxy Issue -> Binance Error (-1000, -1001)
- **Date Reported:** 2024-08-26 6:36:00 AM
- **Severity:** Critical
- **Problem:** `Binance Error` when send bulk order requests.
- **Cause:** GCP Rollout Updates -> Not enough RAM to run proxy -> proxy is terminated.
- **How to resolve:** Ensure whenever there are any issues with Proxy, core backend still works well.
- **Action items:**
  1. Auto remove the inactive proxy and retry on others.
  2. Proxy health check and monitoring.

---
 
### Invalid IP 34.142.207.78
- **Date Reported:** 2024-08-27 7:54:00 PM
- **Severity:** High
- **Problem:** `Invalid API-key, IP or permission for action, request ip: 34.142.207.78` error when send bulk order requests.
- **Cause:** Bunny whitelist IP doesn't include 34.142.207.78.
- **How to resolve:** Update whitelist IP of Bunny account.
- **Action items:**
  1. Update Bunny whitelist IP.
  2. Double check whitelist IP of others and documentation.

---
 
### Timeout Error
- **Date Reported:** 2024-08-27 01:00:00 AM
- **Severity:** High
- **Problem:** `Timeout error` when send bulk order requests.
- **Cause:** Unknown. Assumption: failed to connect proxy.
- **How to resolve:** Restart server and monitoring.
- **Action items:** Restart server and monitoring.

---
