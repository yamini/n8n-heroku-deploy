# n8n-heroku-deploy

> Forked from https://github.com/sarveshpro/n8n-heroku and https://github.com/UnlyEd/n8n-heroku-demo  

 ![Docker](https://github.com/yamini/n8n-heroku-deploy/workflows/Docker/badge.svg) ![Heroku](https://github.com/yamini/n8n-heroku-deploy/workflows/Heroku/badge.svg)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/man0l/n8n-heroku-deploy)


### What does this repo do?
This is a [Heroku](https://heroku.com/) focused container implementation for [n8n](https://n8n.io/). Just connect your fork of this repo to heroku and let it work its charm!


### Updates & fixes to original repo

1. Updated node.js and n8n versions in Dockerfile

![Dockerfile screenshot](https://p132.p1.n0.cdn.getcloudapp.com/items/z8uO6xnw/9245aaf4-c6bd-41dc-93e4-daa94aca8644.jpg?v=662341673999c036dfe6cc0eaae9104f)
 
2. Updated app.json to address some bugs. 


### How to
1. Fork the repo then make version or config changes. 
2. You can change the following variables in the UI (or in app.json before deploying to Heroku)

* Change user name and password from the default user/pass. 

![user pass screenshot](https://p132.p1.n0.cdn.getcloudapp.com/items/Z4uKoY8J/6ca10242-3f78-417a-b627-cd57d0e567bb.jpg?v=970f1d3cb51a57365a42e6f9a20f7a9f)

* Generate a random string for N8N_ENCRYPTION_KEY value and replace the placeholder . This prevents a credentials error each time you fire up n8n. [Details](https://www.notion.so/n8n-to-heroku-648b270a92524949a5f45bf1261c63f1#3386127000fc4de4837f6c8e907fc7d9). Random string generator: https://www.random.org/strings/?mode=advanced 

![random string screenshot](https://p132.p1.n0.cdn.getcloudapp.com/items/jkuPLQWX/2226d591-0d8c-4e56-9bf9-cae63af43340.jpg?v=5ba751955ac36ad6c9c460f4b8781f98)

*  Update WEBHOOK_TUNNEL_URL to match your heroku app url. The format is usually "your-app-name.herokuapp.com". This fixes the problem with webhook urls generated with "localhost" instead of your domain name. More info here: https://github.com/sarveshpro/n8n-heroku/issues/16#issuecomment-779489872 

![app url screenshot](https://p132.p1.n0.cdn.getcloudapp.com/items/z8uO68o1/03f29f3b-f307-4835-98e2-8a7f1e8715f7.jpg?v=abbe83c03160bfc87d89e24766975230)

3. Click the "Deploy to Heroku" button, log in, configure the app and environment variables (if you haven't done it in app.json). The app will be ready to launch in about 5 minutes. 

### Note
If you're using the free/hobby plan, your app will go to sleep in about 20 minutes. You won't lose any data and it will take around 10-20 seconds to wake back up. If you want to run timed workflows, you can use a service like https://cron-job.org to wake up your app whenever you need it. When you're using an external cron job, you won't need the Cron node inside n8n. I use a webhook instead.


### What is n8n (Nodemation?)
[n8n](https://n8n.io/) is a fair code, workflow automation tool that allows you to connect any API with another, without having to do much coding. Think of it as Zapier on steroids, without the price tag. They also have a fully managed cloud version that's extremely affordable. This heroku build is great for evaluating n8n, sharing workflows with team members and getting to know the internals, but I'd encourage you to sign up and support n8n once you're done testing (I'm not an affiliate, just a fan.)


### Sources

https://github.com/n8n-io/n8n
