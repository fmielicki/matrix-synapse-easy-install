# matrix-synapse-easy-install
Script for Debian based systems to easily install Matrix-Synapse

# What it does
This script installs the latest matrix-synapse distribution from the official repository and spins up a usable Matrix server on your machine. This is bare bones and to the point. This does not come with any creature comforts like Element or Jitsi.

* Install and configure nginx
* Obtain a Let's Encrypt certificate and configure nginx correctly
* Install matrix-synapse-py3
* Configure nginx as a reverse proxy to serve Matrix requests

# What do I need
* A server that runs a reasonably modern Debian based OS. Tested on Debian Stable 10.8.
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

For the lazy folks, running this script unchecked, this is a one-liner which should do it (please note that this requires wget which might not come with e.g. Debian):  
``wget https://raw.githubusercontent.com/ephidrineon/matrix-synapse-easy-install/main/matrix-synapse-easy-install.sh && chmod +x ./matrix-synapse-easy-install.sh && sudo ./matrix-synapse-easy-install.sh``


