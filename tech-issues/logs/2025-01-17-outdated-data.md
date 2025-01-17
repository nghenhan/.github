### Trading data is out synced or delayed (specially for trading volume)
- **Date Reported:** 2025-01-17 1:30:00 PM
- **Severity:** High
- **Problem:** `Trading data is not updated in real-time` after idle for a long time or orders executed.
- **Cause:**
  - Binance sockets don't send enough data to update trading data.
  - The system doesn't have a mechanism to re-syncing data when the internet is interrupted.
  - Backend data is out of date with the latest data from Binance.
- **Proposed solution:** TBD
- **Action items:** TBD