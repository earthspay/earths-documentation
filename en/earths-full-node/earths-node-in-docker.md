# Earths Node in Docker

The easiest way to **run a Earths Node** is by using the new **Earths Docker container**. It requires just **one command** to enable everything or to change the settings of the node.

## Prerequisites

You need to install the latest version of Docker.

Please, follow installation istructions at [Docker Site](https://docs.docker.com/engine/installation/).

## About the image

* This Docker image contains scripts and configs to run Earths Node from **Version 0.13.0 **for TESTNET, MAINNET or CUSTOM networks.
* The image is focused on fast and convenient deployment of Earths Node.
* Container downloads `.jar` file and configuration files from the [releases section](https://github.com/earthspay/Earths/releases) and runs it.

## Running the image

It is highly recommended to read more about [Earths Node configuration](https://docs.earths.ga/en/earths-full-node/how-to-configure-a-node.html) before running the container.

The simplest way to run a container:
```
docker run -it earthspay/node
```

**Note: We recommend to start a container like below for MAINNET:**
```
docker run -p 7779:7779 -p 7778:7778 -e EARTHS_NETWORK=MAINNET -e EARTHS_LOG_LEVEL=DEBUG -e EARTHS_HEAP_SIZE=2g -v YOUR_LOCAL_PATH_HERE:/earths earthspay/node    
```

**For TESTNET:**
```
docker run -p 7779:7779 -p 7773:7773 -e EARTHS_NETWORK=TESTNET -e EARTHS_LOG_LEVEL=DEBUG -e EARTHS_HEAP_SIZE=2g -v YOUR_LOCAL_PATH_HERE:/earths earthspay/node    
```

**You can run container with predefined environment variables:**

|Env variable                 |Description   |
|-----------------------------|--------------|
|`EARTHS_WALLET_SEED`               |Plain text seed for node wallet. Container converts it to base58.   |
|`EARTHS_WALLET_SEED_BASE58`        |Base58 encoded seed.   |
|`EARTHS_WALLET_PASSWORD`           |Password for wallet file.    |
|`EARTHS_VERSION`                   |Node version. Default value is `latest`. You can find the list of available versions [here](https://github.com/earthspay/Earths/releases).|
|`EARTHS_NETWORK`                   |Available values are `MAINNET` and `TESTNET`.   |
|`EARTHS_LOG_LEVEL`                 |Node logging level, available values: `OFF`, `ERROR`, `WARN`, `INFO`, `DEBUG`, `TRACE`. More details about logging are available [here](https://docs.earths.ga/en/earths-full-node/logging.html).   |
|`EARTHS_HEAP_SIZE`                 |Java Heap Size limit in -X Command-line Options notation (`-Xms=[your value]`). More details [here](https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/jrdocs/refman/optionX.html)   |
|`EARTHS_CONFIG_FILE`               |Path to your Earths Configuration file.   |
|`EARTHS_DECLARED_ADDRESS`          |String with IP address and port to send as external address during handshake. Could be set automatically if UPnP is enabled. If `declared-address` is set, which is the common scenario for nodes running in the cloud, the node will just listen to incoming connections on `bind-address:port` and broadcast its `declared-address` to its peers.|
|`EARTHS_AUTODETECT_ADDRESS`        |Set `yes` if you want to get your public address and set value `declared-address` with it.|
|`EARTHS_AUTODETECT_ADDRESS_PORT`   |`EARTHS_AUTODETECT_ADDRESS` can get only an IP address of the node, but not port number, so define your real port number with this variable.|

**Note: All variables are optional.**  

## Configuration

The image supports config customization with env variables.
Depending on env values the image generates `local.conf` file and stores it in `/earths/configs` directory.
The simple rule of how to set a value in the configuration file:
0. Determine the path to variable in configuration file ([complete configuration file](https://docs.earths.ga/en/earths-full-node/how-to-configure-a-node.html))
1. Join all section names with two underscores(`__`).
2. Replace all dashes with one underscore (`_`).
3. Capitalize the final string.

For instance, if you want to set the value of `earths.rest-api.enable`, pass an environment variable `EARTHS__REST_API__ENABLE=no`;
