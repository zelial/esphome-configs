# esphome-configs
my configs for various ESPHome devices

# Prereqs
podman pull esphome/esphome


# ESPHome Web dashboard
Might need to tweak (turn off) selinux to be able to read user home from inside the container 

```podman run --rm --net=host -v "${PWD}":/config -it esphome/esphome```


# cmdline config flash
might need to tweak (turn off) selinux to be able to read user home from inside the container

might need to adjust (chmod a+rwx /dev/ttyUSBXXX) permissions to device

```podman run --rm --net=host -v "${PWD}":/config:Z -it --device=/dev/ttyUSBXXX esphome/esphome run your-config.yaml```

# Sync local config dir with krapnik's for ESPHome WebUI
rsync -avzP --delete  ./ root@krapnik.zelial.cz:/home/esphome/config/
