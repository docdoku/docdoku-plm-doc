docdoku-plm-doc
===============

This project handles the DocdokuPLM user-guide and documentation.

## Build requirements

Ruby, Jekyll 2.0.3, nodejs, git, grunt, bower

### Jekyll

Install jekyll from ruby gem

	[sudo] gem install jekyll -v 2.0.3 

Won't build if using a recent version of jekyll (>= 3.0.0)

### NodeJS

Use latest LTS version

### Git

Latest

### Grunt and Bower

Latest


## Configuration

Please edit the \_config.yml file if you plan to deploy on a different path than server root

To build the doc, run 

	npm run build

To develop, use
	
	npm run dev
