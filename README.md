# racion

Python script to list the video URL for [Ruby Tapas](https://www.rubytapas.com/) episodes.

## Prerequisites

Install [Requests](http://docs.python-requests.org/en/master/) and [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/).

    pip install requests beautifulsoup4

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

Print the episode titles:

    ./racion 400 410

Enable debug logging:

    ./racion --log=DEBUG 400 410

See the help:

    ./racion -h
