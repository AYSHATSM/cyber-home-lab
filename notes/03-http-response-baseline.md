# HTTP Response Baseline

## Objective
Measure the basic HTTP response characteristics of the
local OWASP Juice Shop training application.

## Target
http://127.0.0.1:3000/

## Tool
curl

## Command
curl -sS -o /dev/null -w \
'HTTP status: %{http_code}\nContent type: %{content_type}\nResponse size: %{size_download} bytes\nResponse time: %{time_total} seconds\n' \
http://127.0.0.1:3000/

## Observed Results
- HTTP status: 200
- Content type: text/html; charset=UTF-8
- Response size: 9393 bytes
- Response time: 1.342417 seconds

## Analysis
The server returned a successful HTTP response containing HTML.
The measured response time represents one request and is not
a reliable performance benchmark by itself.

## Limitations
This test measured one request to the application's root route.
It did not evaluate application security, concurrent load,
or performance under different network conditions.

## Next Steps
Repeat the measurement and compare results, then review
additional application behavior within the local lab.

## Repeated Request Measurements

Ten sequential requests were made to the local application.

- Successful HTTP responses: 10 out of 10
- Consistent response size: 9393 bytes per response
- Mean response time: approximately 0.007484 seconds (7.48 ms)
- Fastest response: 0.004583 seconds (4.58 ms)
- Slowest response: 0.012159 seconds (12.16 ms)

## Interpretation

All ten requests returned HTTP 200 with the same response size.
The measured response times varied between requests.

These measurements describe a small local test only. They do not
establish production performance, capacity, or behavior under load.

## Evidence

- evidence/http-response-samples.csv
