[![Shellcheck](https://github.com/iddqdiddqd/acme.sh-autorenewal-cron/actions/workflows/shellcheck.yml/badge.svg?branch=main)](https://github.com/iddqdiddqd/acme.sh-autorenewal-cron/actions/workflows/shellcheck.yml)

# Cron for SSL/TLS certificate renewal via [acme.sh](https://github.com/acmesh-official/acme.sh)

This shell scipt is intended for usage in `/etc/cron.monthly` or `/etc/cron.weekly` scenarios.

## Requirements

1. [acme.sh](https://github.com/acmesh-official/acme.sh) should be installed
1. web server should be already configured for serving https

## Environment variables

- `MONITORING_URL` — should be pointing to your cron monitoring webhook (e.g. [Cronitor](https://cronitor.io/)).
- `COMMON_NAME` — hostname which the certificate should be issued for.
- `EC_CURVE` — private key elliptic curve.

## Notes
1. If you prefer a CA other than LE, go ahead and adjust the `sign_csr` function, the `--server` parameter.
1. In case you plan to use RSA keys, go ahead and adjust the `generate_new_key` function.
1. If you use other server than nginx, go ahead and update the restart hooks.
1. If you are not going to use cron monitoring via webhooks, go ahead and remove the calls from the code.

## Credits

- [acme.sh](https://github.com/acmesh-official/acme.sh)
