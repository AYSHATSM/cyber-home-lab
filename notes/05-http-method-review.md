# HTTP Method Review

## Objective

Compare the HTTP responses returned by the local OWASP Juice Shop
application for GET, HEAD, and OPTIONS requests.

## Scope and Method

- Target: http://127.0.0.1:3000/
- Environment: Local cybersecurity training lab
- Tool: curl
- Methods tested: GET, HEAD, OPTIONS

## Results

### GET
- Status: 200 OK
- Response body size: 9393 bytes
- The application returned its HTML page.

### HEAD
- Status: 200 OK
- Content-Length header: 9393
- No response body was observed.
- A dedicated curl -I request completed without an error.

### OPTIONS
- Status: 204 No Content
- Advertised methods: GET, HEAD, PUT, PATCH, POST, DELETE
- No response body was returned.

## Interpretation

The tested endpoint returned successful responses for GET and HEAD,
and returned 204 No Content for OPTIONS.

The OPTIONS response advertises methods but does not establish that
each method can perform an operation without authentication or
authorization. Those controls were not tested.

An earlier loop using curl -X HEAD reported an incomplete-response
error. The dedicated curl -I request did not reproduce that error.
Therefore, the available evidence does not establish a HEAD-handling
defect.

## Limitations

This was a limited test of one local endpoint. It does not establish
the behavior of every application route or whether advertised methods
can modify data.

## Evidence

- Command output recorded during the lab session.
