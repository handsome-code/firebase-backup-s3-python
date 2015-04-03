Backup Firebase data to AWS S3
==============================

Forked from Sean Meadows awesome script.

Detailed blog post here: http://www.seanmeadows.com/2014/03/firebase-continuous-backup/

Using python, you can automatically (with cron or heroku scheduler) backup all
your Firebase data and store it safely on AWS S3.

The result is a new .json file in your S3 bucket whenever you run this script.

Install
-------

    virtualenv -p python2.7 --distribute venv
    source venv/bin/activate
    pip install -r requirements.txt


Run
---

Import App's config variables:

    heroku config:pull --overwrite

Then run:

    python backup-firebase.py


ENV
---

The repo managers multiple Heroku Apps.

To define the active Heroku app:

    git config heroku.remote <app_name>

To import App's config variables:

    heroku config:pull --overwrite

To export config variables in .env file to App:

    heroku config:push

Get current config env:

    git config --list

New Apps
--------

To add new apps, create them on Heroku and add new git remote.

    git remote add <app_name> <heroku_git_repo>

To deploy:

    git push <app_name> master

