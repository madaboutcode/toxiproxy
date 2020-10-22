# Toxiproxy

Original documentation here : [Shopify/toxiproxy](https://github.com/Shopify/toxiproxy)

This fork implements the `reset_peer` toxic to reset a connection after the defined interval. 

Here are the commands you need to setup a bad elastic connection that resets every 2 sec

1. download the right version of the server and cli for your platform from [releases](https://github.com/madaboutcode/toxiproxy/releases)
2. start the server
    `./toxiproxy-server`
3. add a proxy to ES
    `./toxiproxy-cli create elastic -l 0.0.0.0:9200 -u elastic-server.example.com:9200`
4. add a 'toxic' that resets the connection every 2 sec
    `./toxiproxy-cli toxic add elastic -n reset -t reset_peer -d -a timeout=2000`
