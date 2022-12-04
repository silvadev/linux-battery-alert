# Battery Alert for Linux

Low battery warning program for Linux users written in bash

## Requirements

-   ~~Dunst [doc](https://dunst-project.org/)~~ [libnotify](https://github.com/GNOME/libnotify)
-   Paplay [doc](https://linux.die.net/man/1/paplay)

## Installation:

1. Clone this project to:

    ```bash
    git clone https://github.com/asapdotid/linux-battery-alert.git ~/.config/battery-alert
    ```

    or

    ```bash
    git clone https://github.com/asapdotid/linux-battery-alert.git ~/.local/bin/battery-alert`
    ```

2. Change options variables (optional):

    - `percent_alert`: change this for battery level percent alert (default 20%).
    - `alert_sound`: change this for baterry alert sound path.
    - `time`: change this for time check interval and realert (default 60 seconds).

3. Setup autostart `battery-alert`:

    - mkdir -p ~/.config/autostart `(if not exist)`
    - nano ~/.config/autostart/Battery-Alert `(editor: nano/gedit/vim/nvim)`

        ```bash
        [Desktop Entry]
        Name=Battery-Alert
        Comment=Notification for battery alert
        Exec=~/.config/battery-alert/battery-alert &
        Type=Application
        Terminal=false
        Hidden=false
        ```

        or

        ```bash
        [Desktop Entry]
        Name=Battery-Alert
        Comment=Notification for battery alert
        Exec=~/.local/bin/battery-alert/battery-alert &
        Type=Application
        Terminal=false
        Hidden=false
        ```

4. Restart

## i3wm Setup

Add start `battery-alert` to `i3 config`:

```bash
exec --no-startup-id ~/.config/battery-alert/battery-alert &
```

or

```bash
exec --no-startup-id ~/.local/bin/battery-alert/battery-alert &
```

## Check Battery Alert running

```bash
ps aux | grep battery-alert
```

If any issue please contact me [@asapdotid](mailto:asapdotid@gmail.com) 😃
