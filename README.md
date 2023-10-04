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

# PHP 82

`php artisan module:make one two three four five six seven eight nine ten eleven twelve thirteen fourteen fifteen sixteen seventeen eighteen nineteen twenty twentyone twentytwo twenty-three twenty-four twenty-five twenty-six twenty-seven twenty-eight twenty-nine thirty thirty-one thirty-two thirty-three thirty-four thirty-five thirty-six thirty-seven thirty-eight thirty-nine forty forty-one forty-two forty-three forty-four forty-five forty-six forty-seven forty-eight forty-nine fifty fifty-one fifty-two fifty-three fifty-four fifty-five fifty-six fifty-seven fifty-eight fifty-nine sixty sixty-one sixty-two sixty-three sixty-four sixty-five sixty-six sixty-seven sixty-eight sixty-nine seventy seventy-one seventy-two seventy-three seventy-four seventy-five seventy-six seventy-seven seventy-eight seventy-nine eighty eighty-one eighty-two eighty-three eighty-four eighty-five eighty-six eighty-seven eighty-eight eighty-nine ninety ninety-one ninety-two ninety-three ninety-four ninety-five ninety-six ninety-seven ninety-eight ninety-nine one-hundred`

```bash
# blank project with nwidart modules installed
➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   406.69ms  240.64ms   1.90s    84.54%
    Req/Sec    88.11     58.96   240.00     61.20%
  4770 requests in 5.04s, 332.38MB read
  Socket errors: connect 0, read 0, write 0, timeout 28
  Non-2xx or 3xx responses: 7
Requests/sec:    946.43
Transfer/sec:     65.95MB

# 100 plain modules
➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   403.59ms   92.68ms 736.69ms   84.42%
    Req/Sec    79.97     48.60   470.00     68.80%
  4742 requests in 5.09s, 325.98MB read
Requests/sec:    932.33
Transfer/sec:     64.09MB

# 100 API modules
➜  ~ wrk -t12 -c400 -d5s http://laravel.test
Running 5s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.58s   225.42ms   1.99s    64.71%
    Req/Sec    13.00     10.42    40.00     67.74%
  58 requests in 5.09s, 3.98MB read
  Socket errors: connect 0, read 0, write 0, timeout 41
Requests/sec:     11.40
Transfer/sec:    801.31KB
# Generated optimized autoload files containing 6504 classes

# 100 disabled normal modules
➜  ~ wrk -t12 -c400 -d10s http://laravel.test
Running 10s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   401.20ms  100.45ms   1.03s    87.71%
    Req/Sec    81.01     37.69   290.00     73.80%
  9680 requests in 10.10s, 665.44MB read
Requests/sec:    958.53
Transfer/sec:     65.89MB

# Caching routes

# 211 routes
➜  laravel git:(main) ✗ wrk -t12 -c400 -d30s http://laravel.test
Running 30s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     0.00us    0.00us   0.00us    -nan%
    Req/Sec     4.48      6.04    30.00     94.44%
  106 requests in 30.10s, 7.30MB read
  Socket errors: connect 0, read 0, write 0, timeout 106
Requests/sec:      3.52
Transfer/sec:    248.29KB

# after php artisan route:cache
➜  laravel git:(main) ✗ wrk -t12 -c400 -d30s http://laravel.test
Running 30s test @ http://laravel.test
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.07s   424.97ms   1.96s    80.00%
    Req/Sec     7.66      7.45    70.00     81.67%
  627 requests in 30.04s, 43.21MB read
  Socket errors: connect 0, read 0, write 0, timeout 607
Requests/sec:     20.87
Transfer/sec:      1.44MB

# after cache in swoole, note: CPU usage was WAY lower (7%)
Running 30s test @ http://laravel.test:8000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   341.11ms  564.15ms   1.92s    86.53%
    Req/Sec    16.62    122.00     2.72k    99.55%
  3268 requests in 30.09s, 181.18MB read
  Socket errors: connect 0, read 0, write 0, timeout 2533
Requests/sec:    108.61
Transfer/sec:      6.02MB

# swoole without cache
➜  laravel git:(main) ✗ wrk -t12 -c400 -d30s http://laravel.test:8000
Running 30s test @ http://laravel.test:8000
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   273.13ms  494.40ms   1.74s    86.59%
    Req/Sec    15.67     75.31     1.23k    98.61%
  3242 requests in 30.10s, 179.51MB read
  Socket errors: connect 0, read 0, write 0, timeout 2556
Requests/sec:    107.72
Transfer/sec:      5.96MB
```
