# matrix-synapse-easy-install
Script for Fedora systems to easily install Matrix-Synapse

# What it does
This script installs the latest matrix-synapse distribution from the official repository and spins up a usable Matrix server on your machine. This is bare bones and to the point. This does not come with any creature comforts like Element or Jitsi.

* Install and configure nginx
* Obtain a Let's Encrypt certificate and configure nginx correctly
* Install matrix-synapse-py3
* Configure nginx as a reverse proxy to serve Matrix requests

This does not come with PostgreSQL. Should you want to use PostgreSQL instead of the built-in sqlite database, I'm referring you to the great guide over at matrix-org/synapse: [Using Postgres](https://github.com/matrix-org/synapse/blob/master/docs/postgres.md)

# What do I need
* A server that runs a reasonably modern version of Fedora.
* Correct firewall settings (we need 80, 443, 8008, 8448)
* A domain name with correctly configured DNS records:
```
example.com. IN A IP.OF.YOUR.SERVER
matrix.example.com. IN CNAME example.com.
```
This script handles subdomains perfectly fine, so if you wanted to put matrix on, say, chat.example.com, that will work. In that case, set your DNS entry to ``matrix.chat.example.com``

You do not need to bother with SRV records as this script will configure nginx to serve the .well-known/matrix files dynamically from within nginx itself.

# How to use
Obtain the ``matrix-synapse-easy-install.sh`` file, make it executable and run it.

# Testing and reporting bugs
I'm always looking for people to test my script on different systems.

Tested working on:
* Debian 10
* Ubuntu 20.04

If you're getting bugs or have any other issues, please open an issue or, if you know how to fix it, submit a pull request.
