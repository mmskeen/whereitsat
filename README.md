# whereitsat

A simple application to keep track of where you keep your personal
items. Uses the Flask web development framework, with Google for
login, Bootstrap for styles, X-editable for inline editing, and
SQLAlchemy as an ORM.

## What need does this application fill, and how does it fill it?

Last year I went on a vacation abroad. As I was preparing for the trip, I realized that I wasn't sure where my passport was. Was it somewhere in my closet? Or was it in a box I had in storage at my parents' place on the other side of the country? (It ended up being the latter!) Another scenario: after changing apartments, and as I was about to leave on another trip, I figured it'd be good to make sure I knew where my spare set of car keys was located. After all, you never know when you'll need it. But I couldn't seem to find it. It wasn't in my dresser drawer, or my bookcase, or that one box where I put knick knacks.

If only I'd had whereitsat! This web app is designed to allow you to store information about where you keep valuables, knick knacks, you-name-it! Just go to the website (designed with mobile in mind), type in the item you want to keep track of, and a short description of its location. Or, instead of typing just text (which is so old-school these day!), tell it to use a photo (use one from your phone, or take a new photo) that SHOWS where the item is. Include a description if you want. Either way, you've now recorded where it's at. So next time you go looking for the item, it'll be as easy as checking your whereitsat account and searching the text or looking at your photos!

## Features

The basic functionality is entering, storing, and retrieving and displaying entries of where your item is at, including its name/description, and its location. Of course, we'll keep track of the time for you, for documentation purposes. The app also supports searching the text in your entries, and bringing up results.

The fully fleshed-out project will handle photos (including taking new photos directly from the web page, if you have a camera-capable mobile device.) Ideally, it could also include audio clips.

It is anticipated that within the time frame of this project, the app will also be able to handle photos, but probably not any audio.

## Architecture

As noted above, the app will be built with the Flask web development framework, with Google for login, Bootstrap for styles, X-editable for inline editing, and SQLAlchemy as an ORM.

## Dependencies

- [Flask](http://flask.pocoo.org/)
- [Flask-Login](https://flask-login.readthedocs.org/en/latest/)
- [Flask-OAuth](http://pythonhosted.org/Flask-OAuth/)
- [Flask-SqlAlchemy](http://pythonhosted.org/Flask-SQLAlchemy/)
- [SqlAlchemy](http://www.sqlalchemy.org/)
- [jQuery](http://jquery.com)
- [Bootstrap](https://flask-login.readthedocs.org/en/latest/)
- [X-editable](http://vitalets.github.io/x-editable/index.html)

## Installation

First install a few things through apt:

```
sudo apt-get install python-pip
sudo pip install virtualenv
```

Createa virtual environment:

```
mkdir ~/virtualenvs
virtualenv ~/virtualenvs/whereitsat
source ~/virtualenvs/whereitsat/bin/activate
```

Install Python requirements:

```
pip install -r requirements.txt
```

## Configuration

Copy the configuration file and setup a few important variables:

```
cp doc/config.py .
```

The `SECRET_KEY` is used for securing session state. Generate one
using a Python shell:

```
python
>>> import os
>>> os.urandom(24)
```

Copy this value into the SECRET KEY as a string. Next, create a new
application for Twitter sign-ons using their [developer
page](https://dev.twitter.com/apps).

Be sure to create a callback URL (even a fake one) and check the "Sign
in with Twitter" box. The Consumer key and Consumer secret listed here
should be copied into `TWITTER_KEY` and `TWITTER_SECRET` as strings.

## Run the app

```
python app.py
```

![Screenshot](/static/img/screenshot.png "Screenshot")


