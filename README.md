# quarian
#### control delinquent geth nodes

[Quarian](http://masseffect.wikia.com/wiki/Quarian) is a controller meant to
shepherd Geth instances that are not performing properly, and alert/report on
problems with a Geth instance. If Geth is not running properly, it will
restart Geth with a command of your choosing.

Features:

* **Remote node monitoring via JSON-RPC**: Can monitor remote nodes and issue
  HTTP requests to servers to cause geth restarts. Use the `http-restarter` on
  your Geth client side to easily restart them with the correct command.
* **Easy to read logs**: Nice easy UTF-8 + color logging output to stdout
* **Multiple canonical sources for chain tip**: Supports Etherscan, Etherchain, Infura, and your own geth nodes
* **Modular checks**: Checks are easy to write classes. Turn on and off specific checks.


### Configuration

Settings for Quarian are specified in `settings.conf`. Quarian will look here
for settings, as well as:

* `/etc/quarian/settings.conf`
* `/etc/quarian.conf`
* `/etc/default/quarian.conf`
* `/opt/quarian/settings.conf`

in that order. The `settings.conf` file contains configuration information
for Quarian.

You will want to decide what checks to use for your system, and then add the
check modules you want Quarian to load as the `checklist` property, as a
comma-delimited string (e.g. `cron,chaintip`). If you want to write your own
checks for Quarian, see the README.md inside the `quarian/checks` folder.


### Installation & Use

Quarian is alpha software and is not yet an egg. Quarian is written for **Python 3**. Download and run:

```
pip3 install -r requirements.txt
./quarian.py
```

There are also some argument flags. You can see these by using `quarian.py -h`.


### License

GNU GPL v3.