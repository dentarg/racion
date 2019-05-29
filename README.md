# [ración](https://en.wiktionary.org/wiki/raci%C3%B3n)

Python script to list the video URL for [Ruby Tapas](https://www.rubytapas.com/) episodes.

## Prerequisites

[Pipenv](https://github.com/pypa/pipenv) is used.

    brew install pipenv

Install all dependencies with:

    pipenv sync

Very often, I need to reinstall pipenv, rebuild the virtual environment and then sync:

    brew reinstall pipenv
    pipenv --rm
    pipenv sync

`ENV` values required:

```
RUBYTAPAS_USERNAME=...
RUBYTAPAS_PASSWORD=...
```

## Usage

Give the script the range of episodes you are interested in.

Print the video URLs:

    pipenv run ./racion --videourls 400 410

Download video 400 to 410 with `curl`:

    pipenv run ./racion --videourls 400 410 | ./mk_curl_config | curl -K-

Download video 400 to 410 on remote machine with `curl`:

    pipenv run ./racion --videourls 400 410 | ./mk_curl_config | ssh myserver '(cd /some/dir ; curl -K-)'

Print the episode titles for video 400 to 410:

    pipenv run ./racion 400 410

If end of range is `0`, all available episodes from given start number is displayed:

    pipenv run ./racion 460 0

Enable debug logging:

    pipenv run ./racion --log=DEBUG 400 410

See the help:

    pipenv run ./racion -h
