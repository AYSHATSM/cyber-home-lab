# Test 01: Local Service Discovery

## Objective
Verify that the local OWASP Juice Shop application is
reachable on its expected TCP port.

## Scope
- Target: 127.0.0.1
- TCP port: 3000
- Application: OWASP Juice Shop
- Authorization: Personal local training lab

## Method
Used ss to inspect the local listening socket and
Nmap to identify the service on TCP port 3000.

## Observed Results
- The service was listening on 127.0.0.1:3000.
- Nmap reported TCP port 3000 as open.
- The service returned an HTTP response containing
  the OWASP Juice Shop page.

## Evidence
- ../evidence/nmap-localhost.txt
- ../evidence/http-headers.txt

## Assessment
The test confirms local service availability.
It does not, by itself, establish a vulnerability.

## Recommended Next Step
Inspect the application's HTTP behavior and selected
security headers, then document any verified findings.

## Status
Completed: initial local service discovery.
