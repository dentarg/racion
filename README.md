# [ración](https://en.wiktionary.org/wiki/raci%C3%B3n)

Python script to list the video URL for [Ruby Tapas](https://www.rubytapas.com/) episodes.

## Prerequisites

Install all dependencies with:

    pip install -r requirements.txt

`ENV` values required:

```
RUBYTAPAS_USERNAME=...
RUBYTAPAS_PASSWORD=...
```

## Usage

Give the script the range of episodes you are interested in.

Print the video URLs:

    ./racion --videourls 400 410

Download videos with `curl`:

    ./racion --videourls 400 410 | ./mk_curl_config | curl -K-

Download videos on remote machine with `curl`:

    ./racion --videourls 400 410 | ./mk_curl_config | ssh myserver '(cd /some/dir ; curl -K-)'

Print the episode titles:

    ./racion 400 410

If end of range is `0`, all available episodes from given start number is displayed:

    ./racion 460 0

Enable debug logging:

    ./racion --log=DEBUG 400 410

See the help:

    ./racion -h

## Development

[Setup](http://python-guide-pt-br.readthedocs.io/en/latest/dev/virtualenvs/), first time:

    pip install virtualenv
    pip install virtualenvwrapper
    export WORKON_HOME=~/Envs
    source /usr/local/bin/virtualenvwrapper.sh
    mkvirtualenv racion
    workon racion

Otherwise:

    workon racion

## Dependencies

* [Requests](http://docs.python-requests.org/en/master/)
* [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)
* [html5lib](https://github.com/html5lib/html5lib-python)
