# Benchmarks

```bash
-> wrk -d5s http://laravel.test

Running 5s test @ http://laravel.test
  2 threads and 10 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    43.01ms   55.40ms 355.53ms   80.89%
    Req/Sec   267.67    111.93   570.00     67.00%
  2667 requests in 5.00s, 183.64MB read
Requests/sec:    533.10
Transfer/sec:     36.71MB

# After install, 0 modules

➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   529.20ms  222.50ms   2.00s    82.62%
    Req/Sec    64.62     56.72   440.00     82.86%
  3551 requests in 5.07s, 244.58MB read
  Socket errors: connect 0, read 0, write 0, timeout 3
Requests/sec:    699.80
Transfer/sec:     48.20MB

# 1 module

➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   554.97ms  266.66ms   1.99s    78.08%
    Req/Sec    64.87     68.21   666.00     85.89%
  3346 requests in 5.10s, 230.41MB read
  Socket errors: connect 0, read 0, write 0, timeout 10
Requests/sec:    656.41
Transfer/sec:     45.20MB

# 6 modules

Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   682.12ms  257.68ms   1.84s    79.75%
    Req/Sec    56.66     47.28   280.00     73.55%
  2626 requests in 5.08s, 180.83MB read
  Socket errors: connect 0, read 0, write 0, timeout 23
Requests/sec:    516.92
Transfer/sec:     35.60MB

# 25 modules

➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.08s   538.28ms   1.99s    57.10%
    Req/Sec    26.51     24.90   150.00     81.45%
  846 requests in 5.09s, 58.24MB read
  Socket errors: connect 0, read 0, write 0, timeout 515
Requests/sec:    166.28
Transfer/sec:     11.45MB

# 94 modules (damn you chat gpt)
➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.21s   239.90ms   1.92s    77.78%
    Req/Sec    10.55     12.93    70.00     90.00%
  63 requests in 5.07s, 4.33MB read
  Socket errors: connect 0, read 0, write 0, timeout 45
Requests/sec:     12.43
Transfer/sec:      0.86MB
```