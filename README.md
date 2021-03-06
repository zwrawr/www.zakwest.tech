# ww.zakwest.co.uk
[![Build Status](https://travis-ci.com/zwrawr/www.zakwest.co.uk.svg?branch=develop)](https://travis-ci.com/zwrawr/www.zakwest.co.uk)
[![Coverage Status](https://coveralls.io/repos/github/zwrawr/www.zakwest.co.uk/badge.svg?branch=develop)](https://coveralls.io/github/zwrawr/www.zakwest.co.uk?branch=develop)
[![License: CC BY 3.0](https://img.shields.io/badge/License-CC%20BY%203.0-lightgrey.svg)](https://creativecommons.org/licenses/by/3.0/)

This is the source for my website [www.zakwest.co.uk](https://www.zakwest.co.uk). It's built using Node.js on the server side and preact on the client side. jest and enzyme are used for testing whilst eslint and stylelint are the linters.

![Image of the zakwest.co.uk site](https://zakwest.co.uk/public/files/Github/www.zakwest.tech/www.zakwest.tech.png)

## Development CLI Commands

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# run tests with jest and preact-render-spy
npm run test

# run eslint and stylelint
npm run lint
```

## Folder Structure

- `www.zakwest.tech`
  - `config`
  service files for systemd and config files for apache when using dev.zakwest.co.uk
  - `coverage`
  code coverage reports produced by jest and consumed by coveralls
  - `public`
  files that are made accessable to webrequests by webpack or express
    - `data`
	json files, currently for the link boxes on the home page and the file tree
	- `img`
	all the dynamic/large/raster image assets are here
	- `files`
	all file downloads are served from here
  - `src`
  source code for the site
    - `assets`
	small image assets that can be bake into the build are here
	- `components`
	preact components and their styles
	- `routes`
	preact routes and their styles are here
	- `style`
	Site wide styles (font familys, coulor scheme) are here
  - `server`
  server side code run by node
  - `tests`
  tests for the site
    - `__mocks__`
	testing mocks
	- `__setup__`
	enzyme setup script
	- `components`
	tests for the preact components
	- `routes`
	tests for the preact routes

## Building and Running the pseudo Production enviroment
### Setup
Head over to the [dev.zakwest.co.uk](https://github.com/zwrawr/dev.zakwest.co.uk) repo to find out how to use vagrant to host this project.
The provisioning script deals with all the installation and setup and make the site avaliable at www.dev.zakwest.co.uk .

### Rebuild
To rebuild the site via npm run the following commands.
```bash
    cd /var/www/www.zakwest.tech/
    npm run build
```

### Restart
If changes have been made to the site, then you'll have to restart the node app.
```bash
	sudo service www.dev.zakwest.tech restart
```
If changes have been made to the nginx config, then you'll have to restart nginx.
```bash
	sudo restart nginx service
```

### Clean
To remove all the built files do
```bash
    cd /var/www/www.zakwest.tech/
    npm run clean
```

