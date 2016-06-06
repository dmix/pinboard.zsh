Pinboard.zsh (w/ Qutebrowser userscript support)
---

A simple ZSH script for adding URLs to Pinboard via CLI.

With support for functioning as a [Qutebrowser](https://qutebrowser.org) userscript, create a keyboard short to save the current page to [Pinboard](https://pinboard.in).

### Installation

a) Copy script to a local bin directory, for ex:

    $ git clone https://github.com/t1mxg0d/pinboard.zsh
    $ cp pinboard.zsh/pinboard ~/.bin/pinboard
    $ chmod +x ~/.bin/pinboard

b) Install `curl` if not yet installed

c) Export these two variables to your enviornment:

Visit https://pinboard.in/settings/password and copy/paste your API token as an enviornment variable:

    export PINBOARD_API_TOKEN="<username:apitoken>"

### Usage

To add a URL to pinboard just run:

    $ pinboard add <url>

For example:

    $ pinboard add https://github.com/t1mxg0d/pinboard.zsh/master/README.md
    > Pinboard - Saving: https://github.com/t1mxg0d/pinboard.z....
    > Pinboard - Article saved! {bookmark_id: 732753757}

    Bookmark is now accessible at: https://www.pinboard.com/read/732753757

### Qutebrowser userscript

Copy or symlink `pinboard` to `~/.local/share/qutebrowser/userscripts/` and make executable:

    $ cp pinboard ~/.local/share/qutebrowser/userscripts/
    $ chmod +x ~/.local/share/qutebrowser/userscripts/pinboard

Test it out by running:

    :spawn --userscript pinboard qute-add

Add a keyboard shortcut by opening `~/.config/qutebrowser/keys.conf`

    vim +437 ~/.config/qutebrowser/keys.conf

and copying this into the [normal] section (line 47-437).

    spawn -u pinboard qute-add
        sI

Now open Qutebrowser and test out the keyboard shortcut. You can change `sI` so whatever keyboard shortcut you like.

- Enjoy!
t1mxg0d

Licence: GPL v3
