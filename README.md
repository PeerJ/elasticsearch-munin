# Munin plugin for elasticsearch

A useful Munin plugin for monitoring elasticsearch 1.x nodes in Perl.<br />
This original codes has out of maintenance, so I have started maintenance this plugin.

## Plugins

* elasticsearch_cache - field and filter cache stats

## Configuration

### Variables

* env.host - a elasticsearch node capable of providing stats interface (default localhost)
* env.port - elasticsearch HTTP API port (default 9200)

### Example Config

setup this config adding into `/etc/munin/plugin-conf.d/munin-node` before install.

```
[elasticsearch_*]
env.host 10.1.2.14
env.port 9200

[elasticsearch_open_files]
user root
env.host 10.1.2.14
env.port 9200
```

## Install

Install this plugins with following steps after config setuped.

```sh
# For centos
$ cd /usr/local/src/
$ git clone https://github.com/y-ken/munin-plugin-elasticsearch.git
$ cd munin-plugin-elasticsearch
$ cp -p elasticsearch_* /usr/share/munin/plugins/
$ ln -s /usr/share/munin/plugins/elasticsearch_* /etc/munin/plugins/
$ sudo -H munin-node-configure --shell | grep elasticsearch | sudo -H sh
$ munin-node-configure | grep elasticsearch
$ service munin-node restart
```

## Copyright

Original code has imported from https://gist.github.com/2159398 (made by [@rafl](https://github.com/rafl))

## Licence

MIT License