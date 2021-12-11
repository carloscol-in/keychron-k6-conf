# keychron-k6-conf
Some configurations needed to make my Keychron K6 Keyboard work properly in Linux.

## Enable Fn2 key yield `F1`..`F12` on `Fn2`+`1`...`Fn2`+`=` on Windows Layout

Create the service file: `/etc/systemd/system/keychron.service`. Inside create the service configuration like this:

```
[Unit]
Description=Service to make the Keychron K6 Fn2 key work properly on Windows Layout

[Service]
Type=oneshot
ExecStart=/bin/bash -c "echo 0 > /sys/module/hid_apple/parameters/fnmode"

[Install]
WantedBy=multi-user.target
```

## Enable FastConnectable for BlueTooth

Find the option FastConnectable in the file `/etc/bluetooth/main.conf`. Uncomment it and set it to `true` instead of `false`
