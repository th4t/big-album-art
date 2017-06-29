# big-album-art
A Flask app to display almost-fullscreen album art for your currently playing Spotify songs. Enjoy the visuals!

Work in progress.

## Setup
Use Python 3.5.2

On Ubuntu 16.04 you'll need the following additional packages:
* libpq-dev
* python-dev
* (maybe some more)

Install python dependencies with, preferably in a virtualenv
```
$ pip install -r requirements.txt
```

## Develop

Run app with 
```
$ FLASK_APP=baa/main.py flask run
```

Access it on [localhost](localhost:5000)

## Add New Dependencies

```
# install em with pip in the venv
$ pip freeze --local > requirements.txt
```

## Env Variables

To get the app running, be sure to set following variables:
```
export SPOTIFY_CLIENT_ID="???" #adjust the '???' part for it to work
export SPOTIFY_CLIENT_SECRET="???"
export SPOTIFY_REDIRECT_URL="http://localhost:5000/callback"
export SECRET_KEY="super secret key"

export POSTGRES_URL="127.0.0.1:5432"
export POSTGRES_USER="postgres"
export POSTGRES_PW="dbpw"
export POSTGRES_DB="test"
export REDIS_URL="127.0.0.1:6379"

```

## Links

Used:
* http://flask-sqlalchemy.pocoo.org/2.1/
* https://flask-login.readthedocs.io/en/latest/
* https://developer.spotify.com/web-api/authorization-guide/

Maybe someday:
* https://flask-admin.readthedocs.io/en/latest/

## TODOs

* check if the token has expired with a simple request, handle updating it gracefully
* JS makes too many requests - something might be stacking up or carrying over
* Maybe switch to using blueprints for the fun of it
* Admin interface for the same reason
* Tests
* CI
* Logging
* Sentry for convenient error handling
