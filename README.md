# Contenta Demo using Cardstack

This is a demonstration of how to build an app around [Contenta](http://www.contentacms.org/)) using [Cardstack](https://github.com/cardstack/cardstack).

## Prerequisites

Cardstack is moving toward a fully Dockerized architecture that will reduce this prerequisites list, but here's what you'll need to run it today:

* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/)
* [Yarn](http://yarnpkg.com/)
* [Ember CLI](https://ember-cli.com/)
* [Docker](https://www.docker.com/)

In addition, you will need to have read-write access to a Contenta site. You can either follow the instructions on http://www.contentacms.org/ or try a Docker-based setup like https://github.com/ef4/contenta_docker

## Installation

* `git clone <repository-url>` this repository
* `cd contenta_cardstack`
* `yarn install`

## Running / Development

0. Log into Contenta and configure [Simple Oauth](https://www.drupal.org/project/simple_oauth).

1. You need to have runnign elasticsearch. You can either download and run it manually, or start up a preconfigured local elasticsearch via:

        docker run -d -p 9200:9200 cardstack/elasticsearch:dev
    
2. Search for `url` in cardstack/seeds/development/drupal.js and set it to your Contenta site's URL. It defaults to 'http://localhost'.

2. Set the DRUPAL_TOKEN environment variable to a valid oauth2 access token. @cardstack/hub will use this identity when speaking to Drupal (optional passthrough auth is planned but not implemented).

3. `ember serve`

4. Visit your app at [http://localhost:4200](http://localhost:4200).

## Debugging Cardstack Hub

The @cardstack/hub server process runs inside ember-cli in development. To get much more debug out about what it's doing, set the environment variables:

    DEBUG=cardstack/*
    DEBUG_LEVEL=info (or debug or trace)

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
