# Eww-systemd
Basic systemd services to manage eww widget daemon with `systemctl`.

## Installation
Just put `eww.service` and `eww-open@.service` in one of the following `systemd/user` directories:

- `$XDG_CONFIG_DIRS/systemd/user`
- `~/.config/systemd/user`
- `/etc/systemd/user`
- `$XDG_DATA_DIRS/systemd/user`
- `/usr/lib/systemd/user`

For other valid directories see the [systemd.unit](https://www.freedesktop.org/software/systemd/man/latest/systemd.unit.html) ma page.

## Starting the daemon and showing a window
Inside a graphical session execute the following command to start the `eww` daemon:

    systemctl --user start eww

If you want to open the window `bar` in your default configuration file then 

    systemctl --user start eww-open@bar

(this also starts `eww.service` if not active).

## Autostart eww
To sutomatically start the `eww` daemon and open the window `bar` when a graphical session starts then just execute

    systemctl --user enable eww-open@bar
