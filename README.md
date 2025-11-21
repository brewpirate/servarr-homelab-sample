# servarr homelab stack

This repo is an example of how I envisioned using this stack, feel free to make changes and use this as a base to run your own servarr stack.

## Get started

1. clone this repo `git clone --depth 1 https://github.com/brewpirate/servarr-homelab-sample.git`
1. run `git submodule update --init --recursive` to clone the servarr-services repo which contains the service compose files
1. copy `services/env.sample` to `.env` and update with your values
1. copy `services/compose.override.yaml` to `compose.override.yaml` and apply your container modifications here
1. blaa...

## Services

Please see [servarr-services](https://github.com/brewpirate/servarr-services)

## Start

`docker compose up -d`
