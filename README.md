# Upstart / Forever Script generator

Got an ubuntu server & some node services to run? Run this script and get a nice upstart config to use for this.

Based on this [recipe](http://www.exratione.com/2013/02/nodejs-and-forever-as-a-service-simple-upstart-and-init-scripts-for-ubuntu/).

### Usage

    jeff@aer ~/code/node/upstart-forever-tpl> ./new-service
    new-service -d <app directory> -s app.js -l <logfile path>
    Options:
      -d (app directory) [required]
      -s (startup script) [optional, default: app.js]
      -l (log file) [optional, default: /$appdir/$appname/$appname.log]

Once you've generated a config file:

1. sudo cp ./scripts/appname.conf /etc/init/
2. sudo service appname start
3. forever list

### Requirements

* Ubuntu ( needs upstart )
* node.js & npm
* underscore & optimist
* NODE_PATH must be set. To work around this, try something like:
    NODE_PATH=/usr/local/node_modules ./new-service -d /apps/myapp
