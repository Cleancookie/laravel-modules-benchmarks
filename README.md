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

➜  ~ wrk -t12 -c400 -d10s http://laravel.test
Running 10s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   546.42ms  222.14ms   2.00s    88.64%
    Req/Sec    60.83     43.15   550.00     79.74%
  7140 requests in 10.09s, 491.66MB read
  Socket errors: connect 0, read 0, write 0, timeout 24
Requests/sec:    707.63
Transfer/sec:     48.73MB
```