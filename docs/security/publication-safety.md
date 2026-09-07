# Public documentation safety

This repository is intentionally public. Public architecture must be useful without
becoming an inventory of production access paths.

## Allowed

- logical component diagrams and trust boundaries;
- sanitized request, response and configuration examples;
- approximate or aggregated resource counts;
- hardware model and scientific benchmark methodology;
- public API contracts without credentials;
- security controls, data classes and responsible-disclosure guidance.

## Prohibited

- passwords, tokens, session cookies, OAuth client secrets or private keys;
- Android signing keystores or key passwords;
- production `.env` files, database URLs and queue credentials;
- Cloudflare, Railway, Neon, Upstash or Google administrative credentials;
- exact private IPs, management ports, VPN configuration or private hostnames;
- database dumps, real user records, tester lists or account-linked devices;
- phone serials, advertising identifiers, precise location or personal telemetry;
- unredacted logs, support exports or screenshots containing sensitive data;
- confidential grant, procurement or institutional documents.

Public OAuth client identifiers may not be secrets, but they should be documented only
when necessary. Client secrets and signing material are always private.

## Before every release

1. Review the complete diff and newly added binary files.
2. Scan the working tree and Git history for secrets.
3. Confirm examples use reserved domains, fictitious identifiers and placeholders.
4. Remove personal data and precise infrastructure location.
5. Verify planned hardware is labeled proposed or expected.
6. Rotate any credential that may have been committed, even if later deleted.
7. Obtain institutional review for branding, grants and partnership claims.
