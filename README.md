# WebSight
## Web application for monitoring and analyzing of the behavior of users of websites


[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

WebSight is a NodeJS based web application and JavaScript library for monitoring and analyzing of the behavior of users of websites.

## Features (v1.0)
1. Monitoring most clickable sections on the website
2. Monitoring website traffic
3. Access to the WebSight dashboard including:
    * Data charts,
    * List of all owner's monitored websites and information,
    * Heatmap

## Features (v2.0) - uncertain
- Analyzing website's HTML code for:
    * SEO improvement,
    * Finding problems
- Analyzing website's JavaScript errors

## Technologies

WebSight project uses a number of technologies to work properly:

- [NodeJS](https://nodejs.org/en/)
- HTML5
- [SASS (Syntactically Awesome Style Sheets)](https://sass-lang.com/)
- JavaScript
- [Express](http://expressjs.com)
- [MongoDB](https://www.mongodb.com/)
- [Mongoose](https://mongoosejs.com/)
- [Html2Canvas](https://html2canvas.hertzen.com/)

## Installation

WebSight requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd WebSight
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

WebSight is currently extended with the following plugins:

| Plugin | README |
| ------ | ------ |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |


#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

WebSight is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd WebSight
docker build -t <youruser>/WebSight:${package.json.version} .
```

This will create the WebSight image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of WebSight.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=WebSight <youruser>/WebSight:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```
   [PlGa]: <https://github.com/kokoloko13/WebSight/tree/master/plugins/Google%20Analytics/README.md>
