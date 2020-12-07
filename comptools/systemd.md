
    systemctl reboot
    systemctl poweroff
    systemctl emergency
    systemctl default # graphical + multi-user
    systemctl isolate multi-user.target # same

    systemctl status #show status of everything
    systemctl ——failed # list failed tasks only

    # starting/stopping/disabling a service, for example SSH:
    systemctl start sshd.service
    systemctl stop sshd.service
    systemctl restart sshd.service

    systemctl status sshd.service
    systemctl status —l sshd.service # more info with logs

    systemctl disable sshd.service # don't start ssh by default
    systemctl enable sshd.service # start with default runlevel
    systemctl mask sshd.service # never ever start automatically

    journalctl # show all system messages ever
    journalctl —b # show messages since last boot
    journalctl —k # show kernel messages

    # generate a diagram of the booting process:
    systemd-analyze plot > ~/Desktop/boot.svg
