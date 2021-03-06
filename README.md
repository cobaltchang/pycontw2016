[![codecov.io](https://codecov.io/github/pycontw/pycontw2016/coverage.svg?branch=master)](https://codecov.io/github/pycontw/pycontw2016?branch=master)
[![travis-ci status](https://api.travis-ci.org/pycontw/pycontw2016.svg?branch-master)](https://travis-ci.org/pycontw/pycontw2016)

# PyCon TW 2016

This repository serves the website of PyCon TW 2016. This project is open source and the license can be found in LICENSE.

## Getting Started

### Requirements

- Git 1.8+
- Python 3.4+

### Setting up virtualenv

At first, you should make sure you have [virtualenv](http://www.virtualenv.org/) installed.

then, create your virtualenv:

    python3 -m venv venv

Second, you need to enable the virtualenv by

    source venv/bin/activate

If you are using [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org), then you should assign your python path:

    which python3 # Output: /usr/local/bin/python3
    mkvirtualenv --python=/usr/local/bin/python3 pycontw2016

Install all dependencies:

    pip install -r requirements.txt

### Setting up local environment variables

Settings are stored in environment variables via [django-environ](http://django-environ.readthedocs.org/en/latest/). The quickiest way to start is to rename `local.sample.env` into `local.env`:

    cp src/pycontw2016/settings/local.sample.env src/pycontw2016/settings/local.env

Then edit the SECRET_KEY in local.env file, replace `{{ secret_key }}` into any [Django Secret Key](http://www.miniwebtool.com/django-secret-key-generator/), for example:

    SECRET_KEY=twvg)o_=u&@6^*cbi9nfswwh=(&hd$bhxh9iq&h-kn-pff0&&3

### Run web server

After that, just cd to `src` folder:

    cd src

And run migrate and http server:

    python manage.py migrate
    python manage.py runserver

### Run tests

Tests are managed with [pytest-django](http://pytest-django.readthedocs.org/en/latest/tutorial.html). To run tests:

    py.test

To run tests with coverage report:

    py.test --cov=.


## How to contribute

Follow the [GitHub Flow](https://guides.github.com/introduction/flow/), please **DO NOT push the commits into master directly**. Always create branch by the feature you want to update. You are encouraged to submit a pull request for reviewing before merging things into master.

### Internationalisation

Translations are hosted on [Transifex](https://www.transifex.com/pycon-taiwan/pycon-tw-2016/).
