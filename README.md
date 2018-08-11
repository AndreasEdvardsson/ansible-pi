# ansible-pi
Ansible playbook to configure a Raspberry Pi

# Initial setup
After burning the image to sd card

Activate SSH by default:
In boot volume 
$ touch ssh

Connect to WiFi:
In boot volume
$ nano wpa_supplicant.conf

Put this (raspbian stretch):
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
   ssid="MYSSID"
   psk="my  wifi password"
}

On first boot:
raspi-config

Run it:
$ ansible-playbook -s -i hosts ansible-pi.yml
