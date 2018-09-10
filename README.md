# Running it on Heroku

1. Login to heroku
2. Follow this link [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)
3. Add a slack [incoming webhook]
4. Copy the `Webhook URL` into the Heroku config `SLACK_HOOK_URL`
5. Copy the [Bamboo icalendar feed url](https://nulogycorp.bamboohr.com/feeds/manage.php) into the Heroku config `FEED_URL` 
6. Copy the names of the people on your team exactly as they appear in Bamboo into the Heroku config `NAMES` field
separated by semicolons
7. Click Deploy for Free
8. Once it's done deploying click `Manage App`
9. Go to the (Heroku Scheduler)[https://scheduler.heroku.com/dashboard]
10. Configure the Heroku Scheduler to run `ruby bin/awaybot.rb major` daily at `13:00 UTC`

Optionally Connect the Application to Github
============================================

1. Requires that you have access to the Github repository
2. From the application Deploy->GitHub page click `Connect to GitHub`
3. Grant the heroku app access
4. Click on `Enable Automatic Deploys`

# Running it locally

```
  export FEED_URL='https://nulogycorp.bamboohr.com/feeds/feed.php?id=0657ded635930bebe11d91deede7e8fe'
  export SLACK_HOOK_URL='https://hooks.slack.com/services/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'
  export NAMES='Marino Poletine;Sam de Boni;Mark Shaw'
  ruby bin/awaybot.rb major
```
