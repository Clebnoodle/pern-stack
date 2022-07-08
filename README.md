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

## Configuration

To start up Node.js and PostgreSQL on system startup, you must do the following:

```
add any steps to configure node and postgres
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
Hit enter to accept the default settings except for the following prompt:
```
entry point: (index.js)
```
Instead, enter the main name you want your web server file to be.

Next, install express in the directory you created using the following:
```
npm install express
```
