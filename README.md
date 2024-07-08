# stub for temperature sensing on Raspberry Pi and Orange Pi Zero 3

Designed to use in conjunction with <a href="https://adsb.im/home">ADS-B Feeder Image</a> <a href="https://adsb.im/home"><img src="https://adsb.im/static/images/adsb.im.logo.png" height="30" alt="adsb.im homepage"></a>

This tries to avoid having to build Python modules on the SBC that don't come precompiled via PIP - so it includes a venv named `adsbim`.

At this point, it only supports a DHT22 temperature sensor that is connected to the 26/40 pin expansion port on the Raspberry Pi or the 26 pin expansion port on the Orange Pi Zero 3.

For Raspberry Pi the code assumes that the data pin is connected to pin 15, for the Pi Zero 3 it assumes pin 7. The the comments in `temperature.py` for instructions how to change that.

This is at best a rough starting point. To install
- move the files in this repo to `/opt/adsb/extras`
- if using this on a Raspberry Pi, install pigpiod with `sudo apt install -y pigpiod`
- move the `adsb-temperature.service` file to `/usr/lib/systemd/system` and enable it with `systemctl enable --now adsb-temperature`

