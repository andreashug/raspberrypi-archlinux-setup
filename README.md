# Raspberry PI Setup

This Ansible configuration sets up a Raspberry PI 2 with an
encrypted root partition.


## Usage

Playbooks which run on you workstation require the variable `device` to be set
to the SD cards device path (e.g. `/dev/sdX`).

> Note: The playbooks are not replay-safe.


## Steps

1. Insert the SD card into your workstation
2. Identify the device (e.g. `/dev/sdX`)
3. Run the playbook `format-sdcard.yml` to format and partition the SD card.
4. Run the playbook `install-image.yml` to install Arch Linux on the SD card.
5. Run the playbook `config-image.yml` to adjust some basic settings.
6. Put the SD card into the Raspberry PI and boot it.
7. Run the playbook `prepare-encryption.yml`.
8. Insert the SD card into your workstation and run the playbook `encrypt-root.yml`.


## Sources

- <https://wiki.polaire.nl/doku.php?id=archlinux-raspberry-encrypted>
- <https://gist.github.com/pezz/5310082>
- <https://wiki.archlinux.org/index.php/Dm-crypt/Specialties#Remote_unlocking_(hooks:_netconf,_dropbear,_tinyssh,_ppp)>
- <https://gist.github.com/gea0/4fc2be0cb7a74d0e7cc4322aed710d38>
