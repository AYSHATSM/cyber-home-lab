# HTTP Security Header Review

## Objective
Review selected HTTP response security headers on the local
OWASP Juice Shop training application.

## Scope
Target: http://127.0.0.1:3000/
Testing was limited to the local lab.

## Method
Used curl to retrieve the HTTP response headers and filter for
selected security-related headers.

## Observed Results
- HTTP status: 200 OK
- X-Content-Type-Options: nosniff
- X-Frame-Options: SAMEORIGIN
- Content-Security-Policy: not observed in this response
- Referrer-Policy: not observed in this response
- Permissions-Policy: not observed in this response
- Cross-Origin-Opener-Policy: not observed in this response
- Cross-Origin-Resource-Policy: not observed in this response
- Strict-Transport-Security: not observed in this HTTP response

## Initial Analysis
The response includes headers that help mitigate MIME-type
sniffing and cross-origin framing.

Several other headers were not observed in the sampled response.
Their absence alone does not establish a vulnerability. Further
review should consider application behavior, deployment context,
and whether the headers are set on other routes.

Strict-Transport-Security is intended for HTTPS connections,
so its absence from this plain HTTP localhost response is not
by itself a finding.

## Limitations
This was a basic header review of one route. It did not assess
all endpoints, browser behavior, or exploitability.

## Evidence
- evidence/http-headers.txt

## Recommended Next Step
Review the application's behavior and security configuration
within the authorized local training environment.
