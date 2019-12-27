# web benchmark result

## Nginx 1.15 + php 7.0 with fpm mode

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

## ASP .net core 2.*


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
## ASP .net core 2.* self contained build

```
$ wrk -t20 -c400 -d15s http://localhost:5000        
Running 15s test @ http://localhost:5000
  20 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     9.52ms   23.85ms 705.59ms   98.57%
    Req/Sec     2.71k   667.13    13.61k    95.99%
  783663 requests in 15.10s, 578.46MB read
Requests/sec:  51900.62
Transfer/sec:     38.31MB
```

To build self contained 
```
dotnet publish -c Release -r linux-x64 --self-contained

```

## vert.x 3.*  + kotlin 1.* example

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

## Nim lang 1.0 + jester with release build

```
 $ wrk -t20 -c400 -d15s http://127.0.0.1:5000
Running 15s test @ http://127.0.0.1:5000
  20 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     3.35ms    3.08ms 212.11ms   99.10%
    Req/Sec     6.12k     1.14k   25.80k    93.40%
  1817809 requests in 15.09s, 254.84MB read
Requests/sec: 120447.65
Transfer/sec:     16.89MB


```

## playframework 2.*  + scala 2.*

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
## python 3.6 with sanic


```
huzhifeng@palm ~ $ wrk -t12 -c400 -d30s http://localhost:8000
Running 30s test @ http://localhost:8000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    56.04ms   10.76ms 158.80ms   86.74%
    Req/Sec   590.65    133.09     1.00k    78.68%
  211162 requests in 30.08s, 25.58MB read
Requests/sec:   7019.88
Transfer/sec:      0.85MB

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

## golang 1.11 simple httpd

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

## golang 1.13.5 simple httpd

```
PS C:\Users\huzhifeng> bombardier -c 1024 -n 1000000 http://localhost:8080
Bombarding http://localhost:8080 with 1000000 request(s) using 1024 connection(s)
 1000000 / 1000000 [==========================================================================================] 100.00% 84860/s 11s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     86175.88   31500.73  255908.97
  Latency       11.97ms    17.28ms      1.62s
  HTTP codes:
    1xx - 0, 2xx - 1000000, 3xx - 0, 4xx - 0, 5xx - 0
    others - 0
  Throughput:    14.91MB/s
```
## golang 1.13.5 serve static file on disk

```
PS C:\Users\huzhifeng> bombardier -c 525 -n 100000 http://localhost:80
Bombarding http://localhost:80 with 100000 request(s) using 525 connection(s)
 100000 / 100000 [=============================================================================================] 100.00% 12459/s 8s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     12662.04    3465.68   19151.71
  Latency       38.50ms   169.10ms      7.65s
  HTTP codes:
    1xx - 0, 2xx - 99929, 3xx - 0, 4xx - 0, 5xx - 0
    others - 71
  Errors:
    dial tcp [::1]:80: connectex: No connection could be made because the target machine actively refused it. - 71
  Throughput:     3.09MB/s
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

## nginx unit + php 7.0

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

## nginx unit + python 3.*  + django

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

## spring boot 1.5.* + undertow

```
$ wrk -t12 -c400 -d15s http://localhost:8080/
Running 15s test @ http://localhost:8080/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    10.63ms   15.06ms 360.89ms   90.00%
    Req/Sec     4.80k     1.67k   15.77k    70.55%
  854414 requests in 15.10s, 102.01MB read
Requests/sec:  56594.28
Transfer/sec:      6.76MB

```
# Rust

## Actix-web 1.x + debug

```
$ wrk -t12 -c400 -d15s http://localhost:8080/
Running 15s test @ http://localhost:8080/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    33.13ms    8.94ms 270.67ms   74.96%
    Req/Sec     0.99k   169.83     3.65k    80.23%
  175202 requests in 15.07s, 18.21MB read
Requests/sec:  11622.82
Transfer/sec:      1.21MB

```

## Actix-web 2.0 + release

```
 C:\Users\huzhifeng> bombardier.exe  -c5100 -n 100000 http://localhost:8080
Bombarding http://localhost:8080 with 100000 request(s) using 5100 connection(s)
 100000 / 100000 [=============================================================================================] 100.00% 31417/s 3s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     36366.02   59859.52  721275.32
  Latency      160.20ms   143.55ms      1.77s
  HTTP codes:
    1xx - 0, 2xx - 100000, 3xx - 0, 4xx - 0, 5xx - 0
    others - 0
  Throughput:     5.72MB/s
  ```
## Gotham 0.4.0 + debug

```
PS C:\Users\huzhifeng> bombardier.exe  -c500 -n 100000 http://localhost:7878
Bombarding http://localhost:7878 with 100000 request(s) using 500 connection(s)
 100000 / 100000 [=============================================================================================] 100.00% 15565/s 6s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     20113.45   29676.62  250614.00
  Latency       31.69ms   140.99ms      3.73s
  HTTP codes:
    1xx - 0, 2xx - 99962, 3xx - 0, 4xx - 0, 5xx - 0
    others - 38
  Errors:
    dial tcp [::1]:7878: connectex: No connection could be made because the target machine actively refused it. - 38
  Throughput:     3.43MB/s
  ```
  
  ## warp 0.1.18 + debug 
  
  ```
  PS C:\Users\huzhifeng> bombardier.exe  -c500 -n 100000 http://localhost:3030/hello/world
Bombarding http://localhost:3030/hello/world with 100000 request(s) using 500 connection(s)
 100000 / 100000 [=============================================================================================] 100.00% 19295/s 5s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     20325.58   12146.10  100220.49
  Latency       24.88ms   108.53ms      2.96s
  HTTP codes:
    1xx - 0, 2xx - 99962, 3xx - 0, 4xx - 0, 5xx - 0
    others - 38
  Errors:
    dial tcp [::1]:3030: connectex: No connection could be made because the target machine actively refused it. - 38
  Throughput:     3.88MB/s
  ```
