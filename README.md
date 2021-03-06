# What's up, bot?

Check if your Twitter bots are running, get a DM if they aren't.

## For example

Send a DM to @yourname if @examplebot hasn't tweeted in 13 hours.
````
python whatsupbot.py --screen_name examplebot --hours 13 --notify yourname
```

The DM will come from @examplebot, and it will say something like "I'm not working. It's been 14 hours since my last tweet. Fix me!". If everything is running fine, nothing will happen!

Oh yeah, in real life you're going to have to pass in your authentication tokens! Run `python whatsupbot.py --help` for details.

## Installing

At a minimum **What's up bot** requires [tweepy](https://github.com/tweepy/tweepy). Some additional features are unlocked if you install [twitter_bot_utils](https://github.com/fitnr/twitter_bot_utils), which is just a handy wrapper around `tweepy`.

To install twitter_bot_utils, download the repo and run:
```
pip -r requirements.txt
```

Then copy `whatsupbot.py` to somewhere handy.

Install with a cron job, which might look something like this:
```
5 * * * * python $HOME/whatsupbot.py --screen_name botname --notify yourname --consumer-key [etc]
```

## Checking lots of bots

To check lots of bots at once, create a config file, following the format in `config.yaml` (the file can also be JSON, if you prefer). This also gives you a handy place to put your authentication tokens.

Use the `whatsupbot` key to either ignore bots or customize the hours limit on each bot.

Then run:
```
python whatsupbot.py --notify yourname --config config.yaml
```

## Acknowledgments

Thanks to [mattlaschneider](https://github.com/mattlaschneider) for the [https://twitter.com/urbotbroke](urbotbroke) code, and to all the fine friendly folks at #botALLY for being fine friendly folks.
