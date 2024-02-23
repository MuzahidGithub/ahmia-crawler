![https://ahmia.fi/](https://raw.githubusercontent.com/razorfinger/ahmia/ahmia-redesign/ahmia-logotype.png)

Ahmia is the search engine for `.onion` domains on the Tor anonymity
network. It is led by [Juha Nurmi](//github.com/juhanurmi) and is based
in Finland. This repository contains crawlers used by [Ahmia](https://ahmia.fi/) search engine.

# Prerequisites
[Ahmia-index](https://github.com/ahmia/ahmia-index) should be installed and running

# Installation guide

## Install requirements in a virtual environment

```sh
python3 -m virtualenv venv3
source venv3/bin/activate
pip install -r requirements.txt
```

## Prefer own python HTTP proxy

Look fleet installation
[here](https://github.com/ahmia/ahmia-crawler/tree/master/torfleet).

## Configuration

`ahmia/ahmia/example.env` contains some default values that should work out of the box.
Copy this to `.env` to create your own instance of environment settings:

```
cp ahmia/ahmia/example.env ahmia/ahmia/.env
```

# Usage

In order to execute the crawler to run permanently:
```
source venv/bin/activate
./run.sh &> crawler.log
```

# Specific run examples

```sh
scrapy crawl ahmia-tor -s DEPTH_LIMIT=1 -s LOG_LEVEL=DEBUG
or
scrapy crawl ahmia-tor -s DEPTH_LIMIT=1 -O items.json:json
or
scrapy crawl ahmia-tor -s DEPTH_LIMIT=3 -s FULL_PAGERANK_COMPUTE=True
```
