[![Stories in Ready](https://badge.waffle.io/code-computerlove/node-static-site-generator.png?label=ready&title=Ready)](https://waffle.io/code-computerlove/node-static-site-generator)
[![devDependency Status](https://david-dm.org/code-computerlove/node-static-site-generator/dev-status.svg)](https://david-dm.org/code-computerlove/node-static-site-generator#info=devDependencies)
[![Dependency Status](https://david-dm.org/code-computerlove/node-static-site-generator.svg)](https://david-dm.org/code-computerlove/node-static-site-generator)

# Basic static website generator [![Build Status](https://travis-ci.org/code-computerlove/node-static-site-generator.svg?branch=master)](https://travis-ci.org/code-computerlove/node-static-site-generator)

> Get yourself going with a ready made basic static website setup

This repository holds the standard Sass, JavaScript and Testing suite to act as development base.

The site uses [Gulp](http://gulpjs.com) as a task runner along with a few [3rd party tools](docs/3rd-party-plugins.md).

This setup will enable you to run a local node server instance of a website. Through the use of [Handlebars](http://handlebarsjs.com) templating you will be able to compile your website into pre-compiled static HTML files.

It also gives you the ability to package the site up with all the necessary files.

## Installation

* Clone the repo - `https://github.com/code-computerlove/node-static-site-generator.git`
* Open a new command prompt (or Terminal on mac).
* Navigate to the folder
* Run the following commands
    * `npm install` (sudo may be required for mac)
    * `gulp`
    * `gulp serve` - this will open a local instance of the site for you ([See 'Viewing your site'](#viewing-your-site))

Optional setup details can be found in [Welcome](docs/welcome.md)

#### Production and release files.

If you need to compile your templates

* `gulp build --prod`. This will do a full build (HTML compile, style compilation, minification) and output in the `build` folder.
* `gulp release --prod`. This will do the same as the above build task but also package all assets into a zip file in the `release` folder.

adding `--prod` after any command will compress and minify the relevant files.

## Viewing your site

An index has page has purposely been omitted from this setup to encourage you to build from a styleguide.

Ensure you have a local server instance running using `gulp serve`. This creates a local instance of the site and a browser sync instance which proxies off of this.

[Browser Sync](http://www.browsersync.io/) is a tool that allows for painless device testing using a host machine and accessed on port `http://localhost:7000` locally with external devices able to connect to it through the host's ip that is displayed on screen e.g.`192.168.0.1:7000`. Using Browser Sync, any scroll or page interactions are mirrored on all devices and pages are reloaded whenever styles are changed.

The local server can be accessed directly via `http://localhost:3001`

If you have run the `gulp build` task you can navigate to the build folder and open the static HTML files.

## Building your site

#### HTML Template Data

Template data is stored in the `templateData.json` file located in `_config` folder. Anything stored in this file is piped to the handlebars templates under the `data` namespace. If you want to output the value of the key `pageHeading` this would be done via `{{ data.pageHeading }}` (The double brackets tell handlebars to output a dynamic value). As this file is standard json - arrays and objects can be added and used for template loops, passed to partials etc without issue.

## Coding Standards

* [ITCSS (Inverted Triangle CSS)](https://speakerdeck.com/dafed/managing-css-projects-with-itcss)

## Contributing

* [Testing](docs/contributing/testing.md)
