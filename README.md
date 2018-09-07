# Running it on Heroku

1. Login to heroku (FreshBooks employees ask IT for heroku access via OKTA)
2. Follow this link [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)
3. Add a slack [incoming webhook](https://freshbooks.slack.com/services/new/incoming-webhook)
4. Copy the `Webhook URL` into the Heroku config `SLACK_HOOK_URL`
5. Copy the [Bamboo icalendar feed url](https://freshbooks.bamboohr.com/feeds/manage.php) into the Heroku config `FEED_URL`
6. Copy the names of the people on your team exactly as they appear in Bamboo into the Heroku config `NAMES` field
separated by semicolons
7. Click Deploy for Free
8. Once it's done deploying click `Manage App`
9. Click the Edit button beside Add-ons
10. Search for add and save `Heroku Scheduler`
![](https://lh3.googleusercontent.com/syeKOAMs7KJeNJNZU1C0np8b7zLViarMbTxclN3yMFc=w899-h257-no)
11. Go to the (Heroku Scheduler)[https://scheduler.heroku.com/dashboard]
12. Configure the Heroku Scheduler to run `ruby bin/awaybot.rb major` daily at `13:00 UTC`

Optionally Connect the Application to Github
============================================

1. Requires that you have access to the Github repository (FreshBooks employees as in #dev)
2. From the application Deploy->GitHub page click `Connect to GitHub`
![](https://lh3.googleusercontent.com/XskjDMkfdxOG2G9zjn2tmpSzef6qAZk0SSHl8KoQv4w=w922-h595-no)
3. Grant the heroku app access to freshbooks/awaybot
![](https://lh3.googleusercontent.com/Yg3SHpDUS4YEcE1sy2UvrrDSIxSVRQEf37djKvVqrGQ=w923-h444-no)
4. Click on `Enable Automatic Deploys`

# Running it locally

```
  export FEED_URL='https://freshbooks.bamboohr.com/feeds/feed.php?id=SNIP'
  export SLACK_HOOK_URL='https://hooks.slack.com/services/T024K32LX/B060UFKPE/SNIP'
  export NAMES='Sen Nordstrom;Jason Shaw;Jonathan Yee'
  ruby bin/awaybot.rb major
```
