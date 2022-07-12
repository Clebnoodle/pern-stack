# Setting up PERN on Fedora

PERN stands for PostgreSQL, Express, React and Node.js. This tutorial will show you how to setup the entire PERN stack on Fedora.

## PERN Installation

PostgreSQL is available to install through dnf:

```
sudo dnf install postgresql postgresql-server
```

## Node.js Installation

Node.js can be insalled like this:

```
sudo dnf install nodejs
```

## Express

Create and move into folder:

```
mkdir webserver
cd webserver
```

Run the following command to create package.json for your web server:
```
npm init
```
Hit enter to accept the default settings, except for the following prompt:
```
entry point: (index.js)
```
Instead, enter the name you want your main web server file to be. Remember this name for later.

Next, install express in the directory you created using the following:
```
npm install express
```

## Configuration

To start up PostgreSQL on system startup, do the following:

```
sudo systemctl enable postgresql
```


To start up the Express web server on system startup, we will create a script and service.

Make a script called webstart.sh with the following contents:
```
node <path to express file>
ex: node /root/express.js
```
Make sure use the path of the file you created earlier.


Make a service file called express.service in /etc/systemd/system/ with the following contents:
```
[Unit]
Description=Reboot message systemd service.

[Service]
Type=simple
ExecStart=/bin/bash /root/pernStart.sh

[Install]
WantedBy=multi-user.target
```

Now reload your systemctl daemon and enable the service you created:
```
sudo systemctl daemon-reload
sudo systemctl enable express
```
