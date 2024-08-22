# httpd-auth-demo

## Pre-conditions

Update your `/etc/hosts` file to contain an entry for `demo-app.loc`.

## Usage

Execute `docker-compose up -d` from the root of the project.

The following URLs are available:

* [demo-app.loc:9997](http://demo-app.loc:9997) => Direct app access. This demonstrates app functionality without authentication in place. Normally this would not be exposed.
* [demo-app.loc:9998](http://demo-app.loc:9998) => Access Nginx web server. This uses the snipped described [here](https://docs.goauthentik.io/docs/providers/proxy/server_nginx) for a standalone nginx configuration.
* [demo-app.loc:9999](http://demo-app.loc:9999) => Access Apache httpd web server. This demonstrates that the app stack can live behind a HTTPD reverse proxy.

Findings:

* Creating a Authentik provider and application for `http://demo-app.loc:9998` results in a 500 Internal Server error when accessing `http://demo-app.loc:9998`.

