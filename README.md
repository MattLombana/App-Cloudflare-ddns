# App-Cloudflare-ddns

## First Time Prerequisites

1. Generate a cloudflare API key [here](https://dash.cloudflare.com/profile/api-tokens)
    * Give it Zone-DNS-Edit Permissions
    * Resources: Target the zones you would like to use
2. Find the Zone IDs of the zones you would like to use

## Running the Containers

1. Update the following volumes in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/config:/config`
2. Update the following environment vars in [docker-compose.yml](./Docker/docker-compose.yml)
    * `APPRISE=changeme`
    * `CF_APITOKEN=changeme`
    * `CF_HOSTS=test.example.com;test2.example.com`
    * `CF_ZONES=11111111111111111111111111111111;11111111111111111111111111111111` - make sure to use the Zone IDs not the names
    * `CF_RECORDTYPES=A;A`
3. Run `docker-compose -f ./Docker/docker-compose.yml up -d`
