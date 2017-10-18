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

## playframework + scala

```
 $ wrk -t12 -c400 -d30s http://127.0.0.1:9000
Running 30s test @ http://127.0.0.1:9000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    19.81ms   64.62ms   1.96s    99.16%
    Req/Sec     1.96k   763.34     4.57k    70.56%
  499635 requests in 30.09s, 1.18GB read
  Socket errors: connect 0, read 30, write 0, timeout 341
  Non-2xx or 3xx responses: 499635
Requests/sec:  16604.31
Transfer/sec:     40.05MB

```

## python2.7 flask gunicorn

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8000
Running 30s test @ http://127.0.0.1:8000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    28.49ms   63.57ms   1.69s    98.57%
    Req/Sec   569.18    354.72     1.59k    63.86%
  173276 requests in 30.10s, 28.59MB read
  Socket errors: connect 0, read 33, write 0, timeout 37
Requests/sec:   5756.76
Transfer/sec:      0.95MB

```

## python 2.7 flask gevent

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:5000
Running 30s test @ http://127.0.0.1:5000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   146.86ms   31.59ms 373.71ms   75.19%
    Req/Sec   222.23     65.09   656.00     74.53%
  79265 requests in 30.08s, 9.61MB read
  Socket errors: connect 0, read 1, write 0, timeout 0
Requests/sec:   2634.83
Transfer/sec:    327.19KB

```

## golang simple httpd

```
Running 30s test @ http://127.0.0.1:8001
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    18.44ms   29.19ms 480.28ms   88.22%
    Req/Sec     4.52k     2.59k   16.84k    71.61%
  1621767 requests in 30.09s, 303.14MB read
  Non-2xx or 3xx responses: 223
Requests/sec:  53891.72
Transfer/sec:     10.07MB

```

## java 9 + vertx + java + gradle + simple

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8080
Running 30s test @ http://127.0.0.1:8080
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     4.14ms    2.42ms 216.67ms   97.07%
    Req/Sec     8.23k     1.16k   30.34k    93.87%
  2942656 requests in 30.10s, 159.96MB read
Requests/sec:  97771.21
Transfer/sec:      5.31MB

```

## nginx unit + php

```
Running 30s test @ http://127.0.0.1:8300/test.php
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    30.56ms   68.14ms   1.15s    97.17%
    Req/Sec   394.31    168.37     1.23k    69.92%
  139665 requests in 30.10s, 17.32MB read
  Socket errors: connect 0, read 139675, write 1, timeout 0
Requests/sec:   4640.53
Transfer/sec:    589.18KB

```

## nginx unit + python + django

```
$ wrk -t12 -c400 -d30s http://127.0.0.1:8080/        
Running 30s test @ http://127.0.0.1:8080/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    74.89ms  100.00ms   1.20s    96.65%
    Req/Sec   424.73     98.66     0.85k    71.21%
  150655 requests in 30.09s, 1.33GB read
Requests/sec:   5007.25
Transfer/sec:     45.25MB

```
