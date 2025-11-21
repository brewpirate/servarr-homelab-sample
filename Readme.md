# sample servarr homelab stack

This repo is an example of

## Get started

1. clone this repo `git clone --depth 1 https://github.com/brewpirate/servarr-homelab-sample.git`
1. run `git submodule update --init --recursive` to clone the servarr-services repo which are the base
1. copy `..env.sample` to `.env` and update with your settings
1. blaa...

## Structure

```bash
servarr-homelab-sample
├── logs
│   ├── bazarr
│   │   ├── service.log
│   ├── gluetun
│   │   ├── service.log
│   ├── homepage
│   │   ├── service.log
├── services
│   ├── bazarr
│   │   ├── config
│   │   │   ├── config.json
│   │   ├── bazarr-compose.yaml
│   ├── gluetun
│   │   ├── config
│   │   │   ├── config.json
│   │   ├── bazarr-compose.yaml
│   ├── homepage
│   │   ├── config
│   │   │   ├── config.json
│   │   ├── bazarr-compose.yaml
├── user
│   ├── gluetun
│   │   ├── .env
│   │   ├── proton.compose.yaml
│   ├── homepage
│   │   ├── settings.yaml
└── .env
└── compose.override.yaml
└── docker-compose.yaml
```

### Explanation of Key Directories and Files

* **`logs/`**: Contains service logs, this is not container logs
  * **`[service-name]/`**: Each service has its own directory containing the service logs
* **`services/`**: A sub-module [servarr-services](https://github.com/brewpirate/servarr-services) which containes all base service files
  * **`[service-name]/`**: Each service has its own directory containing the service logs, config directory **IS NOT** tracking configuration changes.
* **`user/`**: All configs and settings you want tracked by **your** repo
  * **`[service-name]/`**: Each arr service
    * **`config/`**: Default mapping of service configs
    * **`[service]-compose.yaml`**: Service Docker file
* **`.env`**: Details on the project's architectural design.
* **`compose.override.yaml`**: Specifies intentionally untracked files to ignore.
* **`docker-compose.yaml`**: Lists project dependencies.

## Override Service Settings
