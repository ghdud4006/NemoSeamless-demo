# NemoSeamless-demo

## Installation

Using Autotools:

```
$ cd pebblesdb/src
$ autoreconf -i
$ ./configure
$ make
$ make install
$ ldconfig
```

Using CMake:

```shell
$ mkdir -p build && cd build
$ cmake .. && make install -j16
```

___

## Running microbenchmark
1. `cd pebblesdb/src/`
2. `make db_bench`  (this only works if you are compiling using autotools, and have done `autoreconf` and `configure` before this step)
3. `./db_bench --benchmarks=<list-of-benchmarks> --num=<number-of-keys> --value_size=<size-of-value-in-bytes> --reads=<number-of-reads> --db=<database-directory-path>`  
A complete set of parameters can be found in `db/db_bench.cc`  

Sample usage:  
`./db_bench --benchmarks=fillrandom,readrandom --num=1000000 --value_size=1024 --reads=500000 --db=/tmp/pebblesdbtest-1000`


Use `filter` benchmark property to print the filter policy statistics like memory usage.

`./db_bench --benchmarks=fillrandom,readrandom,filter --num=1000000 --value_size=1024 --reads=500000 --db=/tmp/pebblesdbtest-1000`

```
    fillrandom   :     110.460 micros/op;    9.0 MB/s
    readrandom   :       4.120 micros/op; (5000 of 10000 found)

    Filter in-memory size: 0.024 MB
    Count of filters: 1928
```

___


---
## Contact

Please contact us at `ghdud4006@gmail.com` with any questions.
