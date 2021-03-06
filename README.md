# Webpack2 boilerplate

![webpack2-boilerplate](./webpack2-boilerplate.png)

A Webpack2 boilerplate, partly based on this Egghead.io course; 
[Using Webpack for Production JavaScript Applications](https://egghead.io/courses/using-webpack-for-production-javascript-applications)

## Features
* ES2015
* Node6 or Node7
* Npm as a task/build runner
* Webpack2 with tree-shaking and hot module replacement (HMR)
* Webpack DLL plugin for faster builds
* Express middleware
* Linting with eslint and stylelint
* Unit tests with Mocha, Chai, Sinon and JsDom 
* Code coverage with Istanbul
* SASS boilerplate with Solved by Flexbox Holy Grail example layout
* Self hosting Google Material Icons and Font Roboto
* No dependencies to frameworks like React or Angular
* Uses [husky](https://github.com/typicode/husky) to prevent bad commits

### Husky
This project uses [husky](https://github.com/typicode/husky) to run scripts
before an actual `git commit`

More details about Husky can be found here:
* [Prevent bad git commits and pushes with Husky](http://www.penta-code.com/prevent-bad-git-commits-and-pushes-with-husky/)
* [Prevent Bad Commits with husky](https://davidwalsh.name/prevent-bad-commits-husky)

## Getting started
* Install Node7 or Node6 (via nvm)
* Clone this repository: `git clone https://github.com/leifoolsen/webpack2-boilerplate.git` (or download zip)
* CD to project directory: `cd webpack2-boilerplate`
* Remove existing git: `rm -rf .git`
* Install dependencies: `npm install`
* Build dll: `npm run build:dll`
* Run: `npm start`
* Open a browser at `http://localhost:8084`
* Press `Ctrl+C` to stop the dev server
* Init your git: `git init`
* Modify `package.json`, e.g. `name, author, description, repository` 
* Add your own 3'rd party dependencies  to `package.json`
* Add those 3'rd party dependencies to `./src/vendor.js` or the `entry.vendor` section in **`webpack.config.dll`**
* Happy hacking :)

>**Note:** Remember to add your own repo to package.json 
```
  "repository": {
    "type": "git",
    "url": "https://github.com/<your-git>/<your-project>.git"
  },
```

## NPM Scripts
* `start`: run Express sever with Hot Module Reloading (HMR), eslint and stylelint, serving files at http://localhost:8084
* `test`: run Mocha tests
* `test:watch`: run Mocha tests in watch mode
* `test:single`: run a single Mocha test file in watch mode, e.g.<br/>`npm run test:single test/utils/logger.spec.js`
* `test:pattern`: will run Mocha tests and suites with names matching the given pattern, e.g.<br/>`pattern=logger npm run test:pattern` will run only the `logger` tests
* `test:coverage`: run Istanbul code coverage (open `coverage/lcov-report/index.html` to view coverage report)
* `lint`: lint according to rules in `.eslintrc` and `.stylelintrc`
* `coverage`: runs code coverage 
* `analyze`: run webpack-bundle-size-analyzer to analyze the output bundle sizes
* `clean`: remove the dist directory
* `build`: bundle the app to the dist dir using development settings
* `build:prod`: bundle the app to the dist dir using production settings
* `server`: run Express sever with the generated bundle, serving files at http://localhost:8000
* `precommit`: husky run command for the git pre-commit hook

## Test the bundle
* `npm run build:prod`
* `npm run server`
* Open a browser at `http://localhost:8000`

### Test the API
* Click the "Ping" button or open a browser at `http://localhost:8000/api/ping`. The response should be: `{"ping":"pong!"}`
