# CircleCI-Slack Build Alerts

This application notifies a specific Slack channel when a specific Git branch fails to test on CircleCI.

![](http://i.imgur.com/TVVFOhS.gif)

![](http://i.imgur.com/c4YZSV5.png)

**But can't you do this with a Slack integration already?** Currently, the CircleCI integration will show fixed/failed messages for _all_ branches, which is much too verbose for a large team. Also, we want to make sure that a broken-master alert gets everyone's attention.

## Getting started

1. Follow the [Heroku Getting Started guide](https://devcenter.heroku.com/articles/quickstart) if you haven't already.
1. Clone this repo and `cd` to it.
1. Run `npm install` and then `npm install -g nodemon coffee-script`
1. Create a `.env` file that looks like the sample below.
1. Run `npm run dev`

### Sample `.env` file

    SLACK_WEBHOOK_URL=https://hooks.slack.com/services/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    SLACK_CHANNEL=#eng
    GIT_BRANCH=master

### Deploying to Heroku

1. If creating a new app, run `heroku create` and then set each config var using `heroku config` (read docs [here](https://devcenter.heroku.com/articles/config-vars)]
1. Use `heroku config:set` to set environment variables on the Heroku app.
1. Make sure the app runs locally with Foreman: `foreman start web`
1. To deploy, run `git push heroku`

### Setting up Circle

Set up a notify webhook to the Heroku URL as described [here](https://circleci.com/docs/configuration#notify).

### Credits

* Favicon from [Octicons by GitHub](https://www.iconfinder.com/icons/298789/git_pull_request_icon#size=128)

--------------------------------------------------------------------
Copyright 2015 Artillery Games, Inc. Licensed under the MIT license.
