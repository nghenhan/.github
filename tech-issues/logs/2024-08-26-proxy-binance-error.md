### Proxy Issue -> Binance Error (-1000, -1001)
- **Date Reported:** 2024-08-26 6:36:00 AM
- **Severity:** Critical
- **Problem:** `Binance Error` when send bulk order requests.
- **Cause:** GCP Rollout Updates -> Not enough RAM to run proxy -> proxy is terminated.
- **Proposed solution:** Ensure whenever there are any issues with Proxy, core backend still works well.
- **Action items:**
  1. Auto remove the inactive proxy and retry on others.
  2. Proxy health check and monitoring.