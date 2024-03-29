# passmenu-jsvm

Adaptation of [passmenu], a [dmenu]-based interface to [pass], to better suit my personal way of organising passwords and related info.

## Password store structure

Each _entry_ is comprised of a subdirectory with a `.gpg` file for each _field_.
A field contains a single piece of information, e.g. username, password, url, etc.

## Installation

Clone the repository and symlink `passmenu-jsvm` to a location on your system's `$PATH`, e.g.

```bash
$ ln -s passmenu-jsvm ~/.local/bin/passmenu-jsvm
```


## Usage

  * `passmenu-jsvm`: select an entry, then a field of that entry, then copy it to the clipboard
  * `passmenu-jsvm --type`: select an entry, then a field of that entry, then type it using [xdotool]
  * `passmenu-jsvm --autotype`: select an entry, then type `<username><Tab><password><Ret>` using [xdotool]

Options can be passed to [dmenu] by defining the variable `$DMENU_OPTIONS` in `~/.dmenurc`.
For example, I set the font and colours in mine:

```bash
# ~/.dmenurc

DMENU_FN="RobotoCondensed-12"
DMENU_NB="#2E3440"
DMENU_NF="#D8DEE9"
DMENU_SB="#81A1C1"
DMENU_SF="#2E3440"

DMENU_OPTIONS="-fn $DMENU_FN -nb $DMENU_NB -nf $DMENU_NF -sf $DMENU_SF -sb $DMENU_SB"
```

## Tips

- Bind `passmenu-jsvm --type`/`--autotype` to a key, e.g. <kbd>Super</kbd>+<kbd>p</kbd> for very easy access

[passmenu]: https://git.zx2c4.com/password-store/tree/contrib/dmenu
[dmenu]: https://tools.suckless.org/dmenu
[pass]: https://www.passwordstore.org
[xdotool]: https://www.semicomplete.com/projects/xdotool
