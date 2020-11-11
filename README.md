sudo apt-get update
sudo apt install libncurses5-dev
sudo apt install gcc-avr

cd ~
git clone https://github.com/KevinOConnor/klipper
git checkout v0.9.1
./klipper/scripts/install-octopi.sh
cd ~/klipper/
make menuconfig
make

RENAME ~/klipper/opt/klipper.bin
COPY ~/klipper/opt/renamed-klipper.bin to your SD card and flash your printer

cd ~
git clone https://github.com/Jasrags/klipper-ender-3-v2.git configs
cp configs/printer.cfg.tmpl ./printer.cfg

ls /dev/serial/by-id/*
Add USB id to ./printer.cfg