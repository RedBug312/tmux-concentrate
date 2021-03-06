# tmux-concentrate
Get concentrated on readings.

![The image shows a preview of the plugin.](screenshots/preview.png)

This plugin was inspired by [goyo.vim](https://github.com/junegunn/goyo.vim). Similarly, it creates paddings to the window, in order to limit the contents to a narrower page width.

## Installation

### Install with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @plugin 'RedBug312/tmux-concentrate'

Hit <kbd>prefix</kbd>-<kbd>I</kbd> to fetch the plugin and source it.

### Install Manually

Clone the repo:

    $ git clone https://github.com/RedBug312/tmux-concentrate.git ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/concentrate.tmux

Reload TMUX environment:

    # type this in terminal
    $ tmux source-file ~/.tmux.conf

## Configuration

### Toggle Key

Concentrate mode is toggled by hitting <kbd>prefix</kbd>-<kbd>C</kbd> (Uppercase) by default. You can set `@concentrate-key` to bind it with another key.

    set -g @concentrate-key c

### Background Color

This color will be assigned to all the following options when concentrate mode is enabled.
- `pane-active-border-bg`
- `pane-active-border-fg`

The value is same as that of `window-status-current-bg` by default. You can set `@concentrate-bg` to override it.

    set -g @concentrate-bg black

### Pane Width

The width of concentrated pane is set to be `50%` by default. You can set `@concentrate-width` to override it. You can set the value to either numbers or percentages.

    set -g @concentrate-width 80

The option will fallback to the default value if the specified value exceeds window width.

## How It Works

This plugin simply create two blank panes on the two sides. Noticed that it might fail disabling if you have killed the panes manually before.

![You can see the paddings are actually blank panes in the image.](screenshots/panes.png)

When enabled, `@concentrate-enabled` will be set to record the concentrate mode status of the current window, and might fail if you set the value manually.

## License

[MIT License](https://github.com/RedBug312/tmux-concentrate/blob/master/LICENSE)
