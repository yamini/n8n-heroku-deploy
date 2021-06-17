# n8n-heroku-deploy

> Forked from https://github.com/sarveshpro/n8n-heroku and https://github.com/UnlyEd/n8n-heroku-demo  

 ![Docker](https://github.com/yamini/n8n-heroku-deploy/workflows/Docker/badge.svg) ![Heroku](https://github.com/yamini/n8n-heroku-deploy/workflows/Heroku/badge.svg)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/yamini/n8n-heroku-deploy)


### What does this repo do?
This is a [Heroku](https://heroku.com/) focused container implementation for [n8n](https://n8n.io/). Just connect your fork of this repo to heroku and let it work its charm!


### Updates & fixes to original repo

1. Updated node.js and n8n versions. To update it yourself, fork this repo and modify the Dockerfile

![Dockerfile screenshot](https://p132.p1.n0.cdn.getcloudapp.com/items/z8uO6xnw/9245aaf4-c6bd-41dc-93e4-daa94aca8644.jpg?v=662341673999c036dfe6cc0eaae9104f)
 
3. Updated app.json to fix some bugs. 
4. Before you create the app in Heroku, you will need to update the following variables in the UI (or you can do it in app.json before deploying to Heroku)

* Change user name and password from the default user/pass. 
* Generate a random string and use for the variable N8N_ENCRYPTION_KEY. This prevents a credentials error each time you fire up n8n. [Details](https://www.notion.so/n8n-to-heroku-648b270a92524949a5f45bf1261c63f1#3386127000fc4de4837f6c8e907fc7d9). Random string generator: https://www.random.org/strings/?mode=advanced 
*  Update WEBHOOK_TUNNEL_URL to match your heroku app url. The format is usually your-app-name.herokuapp.com. This fixes the problem with webhook urls generated with "localhost" instead of your domain name. More info here: https://github.com/sarveshpro/n8n-heroku/issues/16#issuecomment-779489872 


### How to
2 easy steps: 
1. Fork the repo then make version or config changes. 
2. Next, click the "Deploy to Heroku" button, log in, configure the app and environment variables. That's it!


### What is n8n (Nodemation?)
[n8n](https://n8n.io/) is a fair code, workflow automation tool that allows you to connect any API with another, without having to do much coding. Think of it as Zapier on steroids, without the price tag. They also have a fully managed cloud version that's extremely affordable. This heroku build is great for evaluating n8n, sharing workflows with team members and getting to know the internals, but I'd encourage you to sign up and support n8n once you're done testing (I'm not an affiliate, just a fan.)


### Sources

https://github.com/n8n-io/n8n
