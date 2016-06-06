Pinboard.zsh (w/ Qutebrowser userscript support)
---

A simple ZSH script for adding URLs to Pinboard via CLI.

With support for functioning as a [Qutebrowser](https://qutebrowser.org) userscript, create a keyboard short to save the current page to [Pinboard](https://pinboard.in).

See also: [instapaper.zsh](https://github.com/t1mxg0d/instapaper.zsh) for a similar script for adding articles to Instapaper via ZSH and Qutebrowser.

### Installation

a) Install `zsh` and `curl` if not yet installed

b) Copy `pinboard` script to a local bin directory or run the installer


    $ git clone https://github.com/t1mxg0d/pinboard.zsh
    $ cd pinboard.zsh
    $ chmod +x install
    $ ./install

c) Export your API token to your shell enviornment:

    export PINBOARD_API_TOKEN="<username:apitoken>"

Visit https://pinboard.in/settings/password to find your API token.

### Usage

To add a URL to pinboard just run:

    $ pinboard add <url>

For example:

    $ pinboard add https://github.com/t1mxg0d/pinboard.zsh/master/README.md
    > Pinboard - Saving: https://github.com/t1mxg0d/pinboard.z....
    > Pinboard - Article saved! {bookmark_id: 732753757}

### Qutebrowser userscript

Symlink `pinboard` bin installed above to `~/.local/share/qutebrowser/userscripts/` and make executable:

    $ ln -sf ~/.bin/pinboard ~/.local/share/qutebrowser/userscripts/pinboard

Test it out by running:

    :spawn --userscript pinboard qute-add

Add a keyboard shortcut by opening `~/.config/qutebrowser/keys.conf`

    vim +437 ~/.config/qutebrowser/keys.conf

and copying this into the [normal] section (line 47-437).

    spawn -u pinboard qute-add
        sP

Now open Qutebrowser and test out the keyboard shortcut. You can change `sI` so whatever keyboard shortcut you like.

- Enjoy!
t1mxg0d

Licence: GPL v3
