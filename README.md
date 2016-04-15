# sinopia-github-oauth
Sinopia authentication plugin with github oauth web flow

This will allow you to auth via github web oauth flow. However, currently it cannot be used with standard sinopia since it requires [this](https://github.com/rlidwka/sinopia/pull/395) pr to be merged, and the official sinopia project seems to be a bit abandoned by its creators.

## Installation
Instead of npm installing sinopia, you'll have to clone [our fork](https://github.com/soundtrackyourbrand/sinopia):

* `$ git clone `
* `$ cd sinopia`
* `$ npm i`
* `$ npm i sinopia-github-oauth`
* Create an [oauth application](https://github.com/settings/applications/new) in github

## Running
Just run `bin/sinopia` from where you cloned sinopia

## Configuration
Add the following in your `config.yaml`
```yaml
middlewares:
  github-oauth:
    client-id: github-app-id # required
    client-secret: github-app-secret # required

auth:
  github-oauth:
    org: soundtrackyourbrand # required, people within this org will be able to auth
    cache-ttl-ms: 60000 # default to 30s if not present
```

## Authenticating
You cannot use `npm login` to authenticate via this method, instead install [sinopia-github-oauth-cli](https://github.com/soundtrackyourbrand/sinopia-github-oauth-cli)
