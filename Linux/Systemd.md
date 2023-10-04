### Logs
the main command is `journalctl`
```bash
$ journalctl  # shows all the logs (very huge log)
$ journalctl --list-boots # shows the boots hashes
$ journalctl -b {hash} # shows the logs of a particular boot
$ journalctl _SYSTEMD_UNIT={service} # shows logs of a given service
$ journalctl PRIORITY=0 # shows the emergency logs only [7 levels]
$ journalctl -f # shows live logs (watch)
```

