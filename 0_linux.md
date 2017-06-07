sudo apt-get update
sudo apt-get upgrade
sudo apt-get install xorg
sudo apt-get install i3
sudo apt-get install chromium

nano ~/.i3/config

exec chromium --temp-profile --no-first-run --kiosk <url>

sudo mkdir /etc/systemd/system/getty@tty1.service.d
sudo nano /etc/systemd/system/getty@tty1.service.d/override.conf

[Service]
ExecStart=
ExecStart=-/sbin/agetty --autologin <user> --noclear %I $TERM

nano ~/.profile

[ "$(tty)" = "/dev/tty1" ] && exec startx

# systemctl set-default multi-user.target
# systemctl set-default graphical.target
