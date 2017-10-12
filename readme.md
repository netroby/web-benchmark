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
## ASP .net core self contained build

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:5000               
Running 30s test @ http://127.0.0.1:5000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    17.79ms   17.43ms 273.90ms   82.50%
    Req/Sec     2.19k   613.12     6.38k    74.39%
  784136 requests in 30.10s, 91.98MB read
Requests/sec:  26054.21
Transfer/sec:      3.06MB

```

To build self contained 
```
dotnet publish -f netcoreapp2.0 -r centos.7-x64 --self-contained

```

## vert.x + kotlin example

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8080
Running 30s test @ http://127.0.0.1:8080
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     3.47ms    2.33ms 220.09ms   98.18%
    Req/Sec     9.75k     1.55k   59.36k    96.70%
  3474947 requests in 30.10s, 172.33MB read
Requests/sec: 115448.83
Transfer/sec:      5.73MB

```
