# Cron for SSL/TLS certificate renewal via [acme.sh](https://github.com/acmesh-official/acme.sh)

This shell scipt is intended for usage in `/etc/cron.monthly` or `/etc/cron.weekly` scenarios.

## Requirements

1. [acme.sh](https://github.com/acmesh-official/acme.sh) should be installed
1. web server should be already configured for serving https

## Environment variables

- `MONITOR_URL` — should be pointing to your cron monitoring webhook (e.g. [Cronitor](https://cronitor.io/)).
- `DOMAIN_NAME` — pretty straightforward.
- `EC_CURVE` — private key curve (`openssl ecparam -list_curves`).

## Notes
1. If you prefer some other CA than LE, go ahead and adjust the code for yourself.
1. In case you plan to use RSA keys, go ahead and adjust the code for yourself.
1. If you use other server than nginx, go ahead and adjust the code for yourself.
1. If you are not going to use cron monitoring via webhooks, go ahead and remove the calls from the code.

## Credits

- [acme.sh](https://github.com/acmesh-official/acme.sh)
