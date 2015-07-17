# Ubunt install Wireshark

```bash
$ sudo apt-get install wireshark
$ sudo dpkg-reconfigure wireshark-common
$ sudo usermod -a -G wireshark $USER
$ sudo reboot
```

Instead of rebooting, you can logout with this command:

- Ubuntu Desktop:
`$ gnome-session-quit --logout --no-prompt`

- Ubuntu Server:
`$ pkill -KILL -u $USER`
