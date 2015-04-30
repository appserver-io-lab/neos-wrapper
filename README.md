# Running TYPO3.Neos on appserver.io

TYPO3.Neos is ready to run on the appserver.io infrastructure right now.

This description assumes that variable $AS points to the root of the appserver.io AS distribution. By default ```/opt/appserver``` on any Linux or Mac OS X system. 

## Issues
In order to bundle our efforts we would like to collect all issues regarding this package in [the main project repository's issue tracker](https://github.com/appserver-io/appserver/issues).
Please reference the originating repository as the first element of the issue title e.g.:
`[appserver-io/<ORIGINATING_REPO>] A issue I am having`

## Installation

This possibility assume that you have a working ANT and a global composer installation running on your 
local machine.

ATTENTION: By calling the ANT target, you'll silently delete a installation that will be found under
```$AS/webapps/neos-1.0.2```. So use this solution only, if you've a backup or can be sure that you
don't need any files from this directory.

To run the ANT target, do the following:

```
$ cd ~
$ git clone https://github.com/appserver-io-lab/neos-wrapper.git
$ cd neos-wrapper
$ sudo ANT init-instance
```

After that, restart the application server and enjoy!

Wait until the application server has been restarted, open a browser and start the setup process by
opening the URL ```http://127.0.0.1:9080/neos-1.0.2/setup```.

## Create the PHAR archive by yourself

Additionally you can create the PHAR archive with the TYPO3.Neos version (you have to specify in the
build.default.properties) by yourself. You will also need a working ANT and a global composer installation
on your local machine.

There you have to do the following steps:

```
$ cd ~
$ git clone https://github.com/appserver-io-lab/neos-wrapper.git
$ cd neos-wrapper
$ sudo ANT create-phar
```

You'll find the resulting PHAR archive in the ```target``` folder.
