# fabsetup

Fabric tasks in order to set up and maintain configurations, software
installations and other things on a local or remote linux system
(most functionality for Debian/Ubuntu).

> _"dotfiles on steroids"_

## Usage

__fabsetup__ is a __[fabric](http://www.fabfile.org/ "www.fabfile.org")__
script.

```sh
# task infos

## list all tasks: '-l'
fabsetup -l

## show details: '-d'
fabsetup -d setup.vim_janus


# run tasks

fabsetup setup.regex_repl

## on your local host:
fabsetup setup.pencil3 -H localhost

## remote host:
fabsetup up -H example.com
```

__[Setup-Howtos](./howtos "cookbook")__:

 * Customize fabsetup: [Initialize git repository
   `fabsetup_custom`](./howtos/fabsetup-custom.md)
 * [Set up an environment without sudo access](./howtos/no-sudo.md)
 * [Webserver Certificates with Letsencrypt](./howtos/letsencrypt.md)
 * [Host an Owncloud Service](./howtos/owncloud.md)
 * [Host an own F-Droid Repository](./howtos/f-droid-repo.md) (Android App Repository)
 * [Host a Selfoss Service](./howtos/selfoss.md) (RSS Reader Web Application)
 * [Install latest Node.js via nvm](./howtos/nodejs.md)
 * [Create or update a reveal.js presentation](./howtos/revealjs.md)
 * __[How to create and write a fabsetup-addon](./howtos/fabsetup-addon.md)__

## Known fabsetup-addons

* [fabsetup-theno-termdown](https://github.com/theno/fabsetup-theno-termdown)

Please contribute:
[Create your own fabsetup-addon](./howtos/fabsetup-addon.md) and make a
[pull request](https://github.com/theno/fabsetup/pulls) which adds your
 fabsetup-addon to the `known_pip_addons` in `fabsetup/addons.py` and to this
`README.md`.

## Installation

As a [pypi package](https://pypi.python.org/pypi/fabsetup)
with command `pip` (recommended way):

```sh
pip install fabsetup

# without superuser privileges
pip install --user fabsetup
```

When running with `--user`, pip installs the command `fabsetup` at
`~/.local/bin`.  [Assure](https://stackoverflow.com/a/14638025) that
`~/.local/bin` is set in your `$PATH` environment variable.

You also can clone the [github repository](https://github.com/theno/fabsetup)
instead of using `pip`:

```sh
# install requirements
sudo apt-get install  git  fabric
pip install --user utlz

git clone  https://github.com/theno/fabsetup.git  ~/.fabsetup

# from ~/.fabsetup dir use `fab` instead of `fabsetup`
cd ~/.fabsetup
fab -l
```

## Development

Devel commands:

```bash
# save changes
git commit -am 'I describe my changes'

# upload to github
git push origin master

# update version number in fabsetup_theno_termdown

# create and publish package at pypi
fab -f fabfile-dev.py  pypi

# clean up
fab -f fabfile-dev.py  clean
```
