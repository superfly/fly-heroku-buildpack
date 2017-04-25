<a href="https://fly.io/slack/"><img src="https://fly.io/slack/badge.svg"></a>

# Fly Heroku Buildpack

Connects any Heroku app to Fly.io network.

## How to get started

Add a new backend on https://app.fly.io/ if you haven't already. You'll need the auth token.

Add a buildpack to your app and configure it:
```
heroku buildpacks:add https://github.com/superfly/fly-heroku-buildpack
heroku config:set FLY_TOKEN=<TOKEN_FOR_YOUR_BACKEND>
```

Deploy your changes:
```
git push heroku master
```

Your Fly backend should now be proxying traffic to your Heroku app. You can use one of the *.shw.io preview links to test that.

Once your app is set-up on Fly, you can stop the ingress traffic to your dyno by changing the process name in the _Procfile_ from `web` to something else.

You can find more details at https://fly.io/docs
