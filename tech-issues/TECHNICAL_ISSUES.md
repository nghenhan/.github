# Technical Issues Guide

## When to Create Issues

Create a technical issue when encountering:
- Production errors affecting trading
- System performance degradation
- Security concerns
- API integration problems
- Critical user-reported bugs

## How to Create Issues

1. Create a new file in `/tech-issues/logs/` with format `YYYY-MM-DD-issue-name.md`
2. Use the appropriate template based on severity
3. Fill all required fields
4. Add to the main TECHNICAL_ISSUES.md index

## Severity Levels

- **Critical:** Trading operations blocked, immediate action required
- **High:** Major feature broken, needs same-day resolution
- **Medium:** Feature partially affected, needs resolution within week
- **Low:** Minor impact, can be scheduled for future sprint

## Issue Templates

```md
### [Issue Title]
- **Date Reported:** YYYY-MM-DD HH:MM:SS AM/PM
- **Severity:** [Critical/High/Medium/Low]
- **Problem:** Brief description of the error/issue
- **Cause:** Root cause analysis
- **Proposed solution:** Step-by-step resolution
- **Action items:** 
  1. Immediate actions
  2. Follow-up tasks
```

## Example Issues

See examples in logs:

- [proxy-binance-error.md](logs/2024-08-26-proxy-binance-error.md)
- [invalid-ip.md](logs/2024-08-27-invalid-ip.md)
- [long-initialization.md](logs/2025-01-17-long-initialization.md)

## Maintenance

- Review issues weekly
- Update status regularly
- Archive resolved issues monthly
- Keep templates updated based on team needs
