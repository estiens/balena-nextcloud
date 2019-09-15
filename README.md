# balena-nextcloud

nextcloud stack for aarch64 on balenaCloud

## Requirements

* RaspberryPi3, RaspberryPi4, or a similar aarch64 device supported by BalenaCloud
* Custom domain name with Cloudflare DNS (eg. nextcloud.mydomain.com)

## Getting Started

To get started you'll first need to sign up for a free balenaCloud account and flash your device.

<https://www.balena.io/docs/learn/getting-started>

## Deployment

Once your account is set up, deployment is carried out by downloading the project and pushing it to your device either via Git or the balena CLI.

### Application Environment Variables

Application envionment variables apply to all services within the application, and can be applied fleet-wide to apply to multiple devices.

|Name|Example|Purpose|
|---|---|---|
|`CF_API_EMAIL`|`foo@bar.com`|(required) Cloudflare account email|
|`CF_API_KEY`|`b9841238feb177a84330febba8a83208921177bffe733`|(required) Cloudflare global API key|
|`TRAEFIK_CERTIFICATESRESOLVERS_CLOUDFLARE_ACME_EMAIL`|`foo@bar.com`|(required) Email address to use for ACME registration|
|`TRAEFIK_PROVIDERS_DOCKER_DEFAULTRULE`|``Host(`{{index .Labels "customLabel"}}.mydomain.com`)``|(required) Replace `mydomain.com` with your domain managed by Cloudflare|
|`NEXTCLOUD_TRUSTED_DOMAINS`|`nextcloud.mydomain.com`|(required) Space-separated list of trusted domains for remote access|
|`MYSQL_PASSWORD`|`nextcloud`|(required) The password that will be set for the MariaDB nextcloud user account|
|`MYSQL_ROOT_PASSWORD`|`my-secret-pw`|(required) The password that will be set for the MariaDB root superuser account|
|`TRAEFIK_LOG_LEVEL`|`DEBUG`|(optional) Log level set to traefik logs|
|`TRAEFIK_CERTIFICATESRESOLVERS_CLOUDFLARE_ACME_CASERVER`|`https://acme-staging-v02.api.letsencrypt.org/directory`|(optional) specify a different CA server to use|

## Usage

_TODO_

## Author

Kyle Harding <https://klutchell.dev>

## Acknowledgments

* <https://hub.docker.com/_/nextcloud/>
* <https://hub.docker.com/_/mariadb/>
* <https://hub.docker.com/_/traefik/>
* <https://go-acme.github.io/lego/dns/cloudflare/>

## License

[MIT License](./LICENSE)
