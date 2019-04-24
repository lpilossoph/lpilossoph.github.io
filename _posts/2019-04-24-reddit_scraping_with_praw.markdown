---
layout: post
title:      "Reddit scraping with PRAW"
date:       2019-04-24 05:57:47 +0000
permalink:  reddit_scraping_with_praw
---


Happy almost summer! I'm going to write briefly about some quick and simple code you can use to scrape data directly from reddit. Away we go!

First we will need to get a username and password, secret id and key. Information on how that is be done can be found here: https://www.reddit.com/wiki/api

Once you've entered your username, password, and secret id/key, you should be connected and ready to scrape some reddit data!

Using the reddit API via praw package returns reddit data in the form of jsons so you must be comfortable working with nested lists and dictionaries to scrape data from reddit!

#connect using praw package: (pip install praw)

reddit = praw.reddit

Now that you are in via praw, here are some fun commands:

reddit.Redditor('name').submissions().new(limit=10)

this command gets you a specific redditors 10 newest submissions 

reddit.Sumbission('id').submission.selftext

this command gets you the actual text in a submission if you pass in the submission id.

submission = reddit.Submission('id').submission
submission.created_utc

this command gives you a timestamp of the local time it was submitted

submission.gilded

returns the gilded status of the submission

submission.comments().hot(limit=5)

returns the hot 5 comments for this submission

That's all for now!! Here is more information on praws documentation: https://praw.readthedocs.io/en/latest/
