curl.exe -i https://jsonplaceholder.typicode.com/todos/1

output
Date: Sun, 16 Aug 2026 12:08:17 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 83
Connection: keep-alive
access-control-allow-credentials: true
cache-control: max-age=43200
etag: W/"53-hfEnumeNh6YirfjyjaujcOPPT+s"
expires: -1
nel: {"report_to":"heroku-nel","response_headers":["Via"],"max_age":3600,"success_fraction":0.01,"failure_fraction":0.1}
pragma: no-cache
report-to: {"group":"heroku-nel","endpoints":[{"url":"https://nel.heroku.com/reports?s=Ya6iQ5LRYJKdfhqb6Gexs3GVj8mO58pwV33XYDvW6AE%3D\u0026sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d\u0026ts=1783567041"}],"max_age":3600}
reporting-endpoints: heroku-nel="https://nel.heroku.com/reports?s=Ya6iQ5LRYJKdfhqb6Gexs3GVj8mO58pwV33XYDvW6AE%3D&sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d&ts=1783567041"
Server: cloudflare
vary: Origin, Accept-Encoding
via: 2.0 heroku-router
x-content-type-options: nosniff
x-powered-by: Express
x-ratelimit-limit: 1000
x-ratelimit-remaining: 999
x-ratelimit-reset: 1783567083
Age: 5
Accept-Ranges: bytes
cf-cache-status: HIT
CF-RAY: a2c052d4e8b7ce46-SIN
alt-svc: h3=":443"; ma=86400

{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
--------------------------------********************************------------------------------------------
input curl.exe -i https://jsonplaceholder.typicode.com/todos/2

output
HTTP/1.1 200 OK
Date: Sun, 16 Aug 2026 12:23:15 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 99
Connection: keep-alive
access-control-allow-credentials: true
Cache-Control: max-age=43200
etag: W/"63-+s0zIP5ZEQN9hypVJUneLybJ+L0"
expires: -1
nel: {"report_to":"heroku-nel","response_headers":["Via"],"max_age":3600,"success_fraction":0.01,"failure_fraction":0.1}
pragma: no-cache
report-to: {"group":"heroku-nel","endpoints":[{"url":"https://nel.heroku.com/reports?s=V9JshRKrFMbF8egelDuZtAHjD4hyOQZNLOXVP%2BjRnjs%3D\u0026sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d\u0026ts=1785323942"}],"max_age":3600}
reporting-endpoints: heroku-nel="https://nel.heroku.com/reports?s=V9JshRKrFMbF8egelDuZtAHjD4hyOQZNLOXVP%2BjRnjs%3D&sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d&ts=1785323942"
Server: cloudflare
vary: Origin, Accept-Encoding
via: 2.0 heroku-router
x-content-type-options: nosniff
x-powered-by: Express
x-ratelimit-limit: 1000
x-ratelimit-remaining: 999
x-ratelimit-reset: 1785323963
Accept-Ranges: bytes
cf-cache-status: REVALIDATED
CF-RAY: a2c068bf6c27fd1f-SIN
alt-svc: h3=":443"; ma=86400

{
  "userId": 1,
  "id": 2,
  "title": "quis ut nam facilis et officia qui",
  "completed": false
}
--------------------------------------------*****************************---------------------------------
input curl.exe -i https://jsonplaceholder.typicode.com/todos/999999

output HTTP/1.1 404 Not Found
Date: Sun, 16 Aug 2026 12:27:33 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 2
Connection: keep-alive
access-control-allow-credentials: true
Cache-Control: max-age=43200
etag: W/"2-vyGp6PvFo4RvsFtPoIWeCReyIC8"
expires: -1
nel: {"report_to":"heroku-nel","response_headers":["Via"],"max_age":3600,"success_fraction":0.01,"failure_fraction":0.1}
pragma: no-cache
report-to: {"group":"heroku-nel","endpoints":[{"url":"https://nel.heroku.com/reports?s=QaQaIRrHMumNBzFr5w3FneOxrh6VzM2zz3Jcuo%2FViTA%3D\u0026sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d\u0026ts=1786883253"}],"max_age":3600}
reporting-endpoints: heroku-nel="https://nel.heroku.com/reports?s=QaQaIRrHMumNBzFr5w3FneOxrh6VzM2zz3Jcuo%2FViTA%3D&sid=e11707d5-02a7-43ef-b45e-2cf4d2036f7d&ts=1786883253"
Server: cloudflare
vary: Origin, Accept-Encoding
via: 2.0 heroku-router
x-content-type-options: nosniff
x-powered-by: Express
x-ratelimit-limit: 1000
x-ratelimit-remaining: 999
x-ratelimit-reset: 1786883265
cf-cache-status: EXPIRED
CF-RAY: a2c06f0a0e681d47-SIN
alt-svc: h3=":443"; ma=86400

{}