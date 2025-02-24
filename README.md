# 🌊 Sea Lion
Sea Lion makes network information available as a data source for p5.js sketches.

To do that, Sea Lion relies on a local server talking to the network and serving information it collects to a JavaScript client. From there, you can use p5.js functions to consume and process the network data however you want.

# Getting started
1. Clone this repository

## Server
For first-time setup with virtualenv:

1. Open up Terminal and `$ cd server` to get to the `sealion/server/` directory
2. `$ virtualenv venv` to create a virtualenv
3. `$ source venv/bin/activate` to activate the virtualenv
4. `$ pip install -r requirements.txt` to install Python dependencies

Start server:

3. `$ python main.py` from `server/src/` directory starts a server on port 8080

## Client

1. In a separate Terminal tab from the server, `cd` to the `sealion/client/` directory
2. Run `$ npm install` to install Node.js dependencies
2. Open `sealion/client/sample-project/index.html` in your browser

# Development
## Server
From `server/`:
- `pip install NEW_PACKAGE && pip freeze > requirements.txt` to save new dependencies

## Client
From `client/`: 
- `$ npm run build` creates `client/dist/main.js`

## Docs
- `docs/` are the source files for the documentation site; make changes to these files and then build them from `website/` with the scripts below

From `website/`:
- `$ npm run start` opens your default browser to a local server on port 3000 so you can see your changes
- `$ npm run build` builds the docs site when everything looks good
- to publish the latest build to gh-pages branch (requires push access to the repo):
```
$ GIT_USER=<GIT_USER> \
  CURRENT_BRANCH=master \
  USE_SSH=true \
  npm run publish-gh-pages
```
- the documentation site was built with [Docusaurus](https://docusaurus.io)

## Tests
Uses pytest

- `$ pytest` from `server/` directory runs tests
- `$ pytest --cov=src` from `server/` creates a coverage report
- add tests to `server/tests/` directory with the naming convention `test_*.py`
