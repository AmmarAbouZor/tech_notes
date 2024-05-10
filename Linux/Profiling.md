## Simple Profiling With Time 

We can use the tool `/usr/bin/time` on Linux to get the profiling info of any command we run. In order to get the verbose information we must call the program with it's full path and not only the build in command `time`

```bash
# get the verbose information
/usr/bin/time -v {Command_or_binary_bath}

# Example to measure ls command
/usr/bin/time -v ls 
```

For memory usage we need to check the value of `Maximum resident set size` 

## Other Tools 

- [Valgrind](https://valgrind.org/) Provide more power full feature for profiling and finding memory leaks
- [cap](https://crates.io/crates/cap) is a crate that can be used within Rust apps to track all memory allocations