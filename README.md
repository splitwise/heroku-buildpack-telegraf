# heroku-buildpack-telegraf
A simple heroku buildpack to download, deploy and launch Telegraf on your dynos

This buildpack downloads the latest Telegraf release (at the time of writing, 1.36.3), extracts it on your dyno and starts it via a .profile.d script.

## Installation
First create a telegraf.conf file in your app's home directory. Take a look at [the docs](https://github.com/influxdata/telegraf/blob/master/docs/CONFIGURATION.md) for instructions on generating and modifying a telegraf configuration file.

Then add the buildpack to the list of heroku buildpacks:

    heroku buildpacks:add --index 1 https://github.com/splitwise/heroku-buildpack-telegraf.git

## Mirrors and custom builds

By default, this buildpack downloads and installs the official Telegraf binary. However, these have become increasingly large, which may use up too much of your Heroku slug size quota.

If you'd like to use a custom build, set `TELEGRAF_DIST_URL_BASE` to the URL where your desired Telegraf tarball is hosted. The buildpack will attempt to download from `TELEGRAF_DIST_URL_BASE/telegraf-1.36.3_linux_amd64.tar.gz`.
