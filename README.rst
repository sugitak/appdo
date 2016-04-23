=======
 appdo
=======

Run your commands in your application context.
Let's eliminate `cd` and `source` in your crontab!

Requirements
============

* Supports Python 2.7 only

We'll be supporting 3.5 soon.

Setup
=====

::

  $ pip install --user appdo
  or
  (venv)$ pip install appdo

Usage
=====

First, write your config file `~/.appdo.conf` in TOML.

::

  [default]
  cd = "~/work/myapp"
  source = ["/etc/profile", "~/.bash_profile"]
  prefix = "bundle exec"

  [default.env]
  PAGER    = "cat"
  RACK_ENV = "staging"

Then run `appdo` command. The commands will be executed in the config manner.

::

  $ appdo rake -vT

Which is equivalent to:

::

  $ cd ~/work/myapp
  $ source /etc/profile
  $ source ~/.bash_profile
  $ PAGER=cat RACK_ENV=staging bundle exec rake -vT


