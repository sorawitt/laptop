Laptop
======

Laptop is a script to set up an OS X laptop for web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* OS X El Capitan (10.11)
* OS X Sierra (10.12)
* OS X Grand Sierra (10.13)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Download, review, then execute the script:

```bash
curl --remote-name https://raw.githubusercontent.com/nimbl3/laptop/master/mac
less mac
bash mac 2>&1 | tee ~/laptop.log
```

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`.
Read through it to see if you can debug the issue yourself.
If not, copy the lines where the script failed into a
[new GitHub Issue](https://github.com/nimbl3/laptop/issues/new) for us.
Or, attach the whole log file as an attachment.

OS X El Capitan (10.11)
-----------------------

You may have problems installing Homebrew for the first time on OS X El
Capitan due to permission changes to the /usr directory (within which the Homebrew
installation is typically located). See the [Homebrew El Capitan troubleshooting instructions](https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/El_Capitan_and_Homebrew.md)
for steps to resolve the permissions issues that interfere with Homebrew's
installation.

What it sets up
---------------

* [Bundler] for managing Ruby libraries
* [Docker] for managing project dependencies
* [hub] for interacting with the GitHub API
* [Heroku Toolbelt] for interacting with the Heroku API
* [Homebrew] for managing operating system libraries
* [ImageMagick] for cropping and resizing images
* [Postgres] for storing relational data
* [RVM] for managing versions of Ruby
* [NVM] for managing versions of Node.JS
* [Redis] for storing key-value data
* [Ruby] stable for writing general-purpose code
* [Tmux] for saving project state and switching between projects
* [Zsh] as your shell
* [oh-my-zsh] to spice up your shell
* [Google Chrome] as teh default browser
* [Slack] to manage communications

[Bundler]: http://bundler.io/
[Foreman]: https://github.com/ddollar/foreman
[hub]: http://hub.github.com/
[Heroku Toolbelt]: https://toolbelt.heroku.com/
[Homebrew]: http://brew.sh/
[ImageMagick]: http://www.imagemagick.org/
[NVM]: https://github.com/creationix/nvm
[RVM]: https://rvm.io/
[Postgres]: http://www.postgresql.org/
[Redis]: http://redis.io/
[Ruby]: https://www.ruby-lang.org/en/
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Tmux]: http://tmux.sourceforge.net/
[Zsh]: http://www.zsh.org/
[oh-my-zsh]: http://ohmyz.sh/
[Docker]: https://www.docker.com/
[Google Chrome]: https://www.google.com/chrome/
[Slack]: https://www.slack.com/

It should take less than 15 minutes to install (depends on your machine).

Customize in `~/.laptop.local`
------------------------------

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh


cask dropbox
cask firefox

brew 'tree'
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,
`brew_install_or_upgrade`, and
`gem_install_or_update`
can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.

Contributing
------------

Edit the `mac` file.
Document in the `README.md` file.
Follow shell style guidelines by using [ShellCheck] and [Syntastic].

```sh
brew install shellcheck
```

[ShellCheck]: http://www.shellcheck.net/about.html
[Syntastic]: https://github.com/scrooloose/syntastic

License
-------

Laptop is © 2014-2018 Nimbl3, Ltd.
It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE

About Nimbl3
----------------

![Nimbl3](https://dtvm7z6brak4y.cloudfront.net/logo/logo-repo-readme.jpg)

This project is maintained and funded by Nimbl3 Ltd.

Inspired by the [project] of thoughtbot.

We love open source and do our part in sharing our work with the community!
See [our other projects][community] or [hire our team][hire] to help build your product.

[project]: https://github.com/thoughtbot/laptop
[community]: https://github.com/nimbl3
[hire]: https://nimbl3.com/
