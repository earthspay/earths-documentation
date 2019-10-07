# Earths Testnet

Testnet is a fully functioning Earths blockchain with the one key exception that because the Earths on the network can be created freely, it has no value. Testnet helps developers test new versions of Earths, as well as test network operations using identical versions of the software before they are carried out on the mainnet.

# Docker container for Earths Testnet node

This Docker image will install the latest release version of Earths Testnet node upon building.

## Building the image

### Prerequisites

You need the latest version of Docker installed.

Please, follow installation istructions at [Docker Site](https://docs.docker.com/engine/installation/).

### Building the image

In order to build a new Docker image execute the following commands:

Clone the project's repository:

```js
git clone https://github.com/earthspay/docker-earths-testnet.git
```

Get into project's directory:

```bash
cd docker-earths-testnet
```

Build an image with the following command:

```bash
docker build -t earths-testnet .
```

### Running the image

List your Docker's images:

```bash
docker images
```

To start a new Docker container, please, execute:

```bash
docker run --name earths-testnet earths-testnet
```

This image defines a storage volume in folder `/data` and volume for configuration file in `/conf` folder. Those folders are persisted on host drive. So, your node configuration and downloaded blockchain will survive the container restart. You can find the locations of volumes on a host computer using `docker inspect` command.

Alternatively you can map volumes on host folders using option`-v`as in:

```bash
docker run --name earths-testnet -v /home/user/local-earths-data:/data -v /home/user/local-earths-conf:/conf earths-testnet
```

In order to use your configuration file you have to place this file in `local-earths-conf` folder and provide the name of the file as command line parameter in `run` command.

```bash
cp my-earths.conf /home/user/local-earths-conf/
docker run --name earths-testnet -v /home/user/local-earths-data:/data -v /home/user/local-earths-conf:/conf earths-testnet my-earths.conf
```

To start and stop the container use Docker commands `docker start earths-testnet` and `docker stop earths-testnet`.

