# heroku-buildpack-telegraf
A simple heroku buildpack to download, deploy and launch Telegraf on your dynos

This buildpack downloads the latest Telegraf release (at the time of writing, 1.2.1), extracts it on your dyno and starts it via a .profile.d script.

## Installation
First create a telegraf.conf file in your app's home directory. Take a look at [the docs](https://github.com/influxdata/telegraf/blob/master/docs/CONFIGURATION.md) for instructions on generating and modifying a telegraf configuration file.

Then add the buildpack to the list of heroku buildpacks:

    heroku buildpacks:add --index 1 https://github.com/splitwise/heroku-buildpack-telegraf.git


