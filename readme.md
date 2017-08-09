# web benchmark result

## Nginx + php with fpm mode

```
$ wrk -t12 -c400 -d30s http://local.domain.com/test.php
Running 30s test @ http://local.domain.com/test.php
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   105.36ms   91.64ms   1.16s    97.57%
    Req/Sec   347.90     53.60     1.82k    87.00%
  123756 requests in 30.10s, 26.31MB read
Requests/sec:   4112.00
Transfer/sec:      0.87MB

```

## ASP .net core


```
$ wrk -t12 -c400 -d30s http://127.0.0.1:5000
Running 30s test @ http://127.0.0.1:5000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    40.30ms   85.06ms 661.01ms   92.35%
    Req/Sec     1.90k     0.85k    4.63k    73.02%
  671031 requests in 30.09s, 78.71MB read
Requests/sec:  22298.28
Transfer/sec:      2.62MB

```
