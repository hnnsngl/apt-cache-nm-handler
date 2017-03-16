# apt-cache-nm-handler

Automatically configure APT to use proxies based on the currently used network. Script can be run for example by the NetworkManger dispatch mechanism.

## Setup and configuration

Copy or symlink the file to `/etc/NetworkManager/dispatch.d/99SetAptProxy` and make sure it is executable there.

The configuration file `/etc/apt-proxies` consists of one line per network in the format `<search domain> <host> <port>`. The network is specified by its search domain found in `/etc/resolv.conf`. The APT cache service is located by the given hostname and port.

## Bugs

Finding the current network via the search domain from `/etc/resolv.conf` can be problematic, when NetworkManager uses its own builtin dnsmasq caching name server.
