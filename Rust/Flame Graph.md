Flame Graph is an extension to cargo to profile anything.

## Install on Ubuntu

On Ubuntu you need to install `perf` dependencies. The current command to install them is: (It's better to check the updated one from FlameGraph Readme)
```bash
sudo apt install linux-tools-common linux-tools-generic linux-tools-`uname -r`
```

When launching it, it could complain about the access is limited on the `perf_event_paranoid`. To fix that you need to set the value for that to a suitable one. (-1) is the full privileges, for my use-case 1 was enough.
You can set that via any of those two commands:

```bash
echo 1 | sudo tee /proc/sys/kernel/perf_event_paranoid
```
or
```bash
sudo sysctl kernel.perf_event_paranoid=1
```