# Security Header Assessment

## Objective

Review selected HTTP response headers from the local OWASP Juice Shop
training application and document security-related observations.

## Scope

- Target: http://127.0.0.1:3000/
- Environment: Local cybersecurity training lab
- Method: HTTP response header inspection with curl
- Evidence: evidence/selected-security-headers.txt

## Observations

1. The server returned HTTP 200 OK.
2. X-Content-Type-Options: nosniff was present.
3. X-Frame-Options: SAMEORIGIN was present.
4. Content-Security-Policy was not observed in the captured response.
5. Permissions-Policy was not observed in the captured response.
6. Referrer-Policy was not observed in the captured response.
7. Cross-Origin-Opener-Policy was not observed in the captured response.
8. Cross-Origin-Resource-Policy was not observed in the captured response.
9. Strict-Transport-Security was not observed in the captured response.
10. Access-Control-Allow-Origin: * was present.

## Risk Interpretation

The missing headers are configuration observations that may warrant
further review. Their absence alone does not prove an exploitable
vulnerability; impact depends on the application, browser behavior,
deployment architecture, and security requirements.

Strict-Transport-Security is intended for HTTPS deployments. Its absence
from this plain-HTTP localhost response is not, by itself, a finding.

The wildcard Access-Control-Allow-Origin value does not alone prove
unsafe CORS configuration. Further review would need to consider the
resources exposed, credentials, and the application's intended access
model.

## Recommendations

- Review whether a Content-Security-Policy can be safely implemented
  and tested without breaking application functionality.
- Review the appropriate Referrer-Policy and Permissions-Policy values.
- Evaluate cross-origin policies against application requirements.
- Assess HSTS on the HTTPS deployment, if one exists.
- Re-test after any configuration changes.

## Limitations

This was a limited review of response headers from one local endpoint.
No exploitability testing or production assessment was performed.

## Evidence

- evidence/selected-security-headers.txt
