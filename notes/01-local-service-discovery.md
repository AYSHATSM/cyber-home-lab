# Local Service Discovery Assessment

## Objective
Verify that the intentionally vulnerable OWASP Juice Shop application is
running locally and document its exposed service and HTTP response headers.

## Scope
Target: 127.0.0.1
Port: TCP 3000
Application: OWASP Juice Shop in a local Docker container

Testing was restricted to the local machine.

## Tools
- Docker
- Nmap
- curl

## Results
- Docker reported the Juice Shop container as running.
- The container port was published on 127.0.0.1:3000.
- Nmap reported TCP port 3000 as open.
- Nmap did not identify the service by its usual service name, but its
  response fingerprint contained an HTTP 200 response and the OWASP
  Juice Shop page content.
- curl returned HTTP/1.1 200 OK.
- HTTP response headers were saved in evidence/http-headers.txt.
- Nmap scan output was saved in evidence/nmap-localhost.txt.

## Initial Observations
The response included Access-Control-Allow-Origin: *, which permits
cross-origin requests under the application's CORS policy. This header
alone does not establish a vulnerability; endpoint behavior and data
exposure would need further testing.

The response also included X-Content-Type-Options: nosniff and
X-Frame-Options: SAMEORIGIN.

## Limitations
This was a basic local service-discovery and HTTP-header check. It was
not a comprehensive security audit, and no exploitability conclusions
were drawn from these results.

## Evidence
- evidence/nmap-localhost.txt
- evidence/http-headers.txt

## Next Steps
Review additional security-relevant HTTP headers and conduct further
controlled tests against the local Juice Shop training application.
