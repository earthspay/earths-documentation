# Installing matcher on Ubuntu from deb-package

## System requirements

- 2 core CPU
- 4 GB RAM
- 50 GB HDD

## Checking OpenJDK version 8 presence

Make sure that you have OpenJDK version 8 installed. To do so, execute the following command in the console

```bash
java -version 2>&1 | grep “openjdk version \“1.8” | wc -l
```

If `0` is being displayed, then proceed to [OpenJDK version 8 installation step](#jdk-install).

If `1` is being displayed, then proceed to [Node installation](#node-install).

## OpenJDK version 8 installation <a id="jdk-install"></a>

To install OpenJDK version 8, execute in a console

```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre
```

## Node installation <a id="node-install"></a>

1. Download the latest version of `waves_<version>_all.deb` file from [https://github.com/wavesplatform/Waves/releases](https://github.com/wavesplatform/Waves/releases).
2. Execute in the console

```bash
sudo dpkg -i /path/to/waves_<version>_all.deb
```

3. Move to `/var/lib/waves` folder by executing

```bash
cd /var/lib/waves
```

## Node setup

1. Open the `/usr/share/waves/conf/waves.conf` file using the command

```bash
sudo nano /usr/share/waves/conf/waves.conf
```

2. Decide whether the existing or new account should be used for [node](/blockchain/node.md). Use the existing account if you plan to use your node as a [mining node](/blockchain/node/mining-node.md).

- To use a new account, uncomment in wallet section the password parameter and set a value for it. Example:

```
wallet {
  # Password to protect wallet file
  password = iAmGoingToUseAnewAccount
  # Wallet seed as BASE58 string
  # seed =
}
```

- To use an existing account, input in wallet section the password and, in base58 encoding, the seed.

```
wallet {
  # Password to protect wallet file
  password = iAmGoingToUseAnExistingAccount
  # Wallet seed as BASE58 string
  seed = 35S7EzKMHMN4JQyWnwpp84Zot1yqLoP2Q46RsbYRzgFq7n8AiV8L6skeGPq93P2NU4pGcZFeNTAT2TKJTa2XvqRwSdCmBR556MBmtZ3ggAkBtd3CCZFvZwZufz1ZqfzJQ
}
```

3. Add to `/usr/share/waves/conf/waves.conf` file the section

```
waves.extensions = ["com.wavesplatform.dex.Matcher"]
```

4. Set in `/usr/share/waves/conf/waves.conf` file in `rest_api` section the following parameters:

- `enable = yes`
- `api_key_hash = " "`

```
rest-api {
  # Disable node’s REST API
  enable = yes
  …
  api_key_hash = " "
}
```

5. Start node by executing

```bash
sudo systemctl start waves
```

6. Generate non-empty `api_key_hash` value. Execute command

```bash
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '<YOUR_ARBITRARY_STRING>' '127.0.0.1:6869/utils/hash/secure'
```

Please use your own value instead of `<YOUR_ARBITRARY_STRING>` (it is recommended to store it). As a result, you will see the following output

```
{"message": "YOUR_ARBITRARY_STRING", "hash": "3QbuM9nJP9GZQDekgfGboPGDQe4g1nsH4kmK2jbCLAFJ"}
```

7. Set in `/usr/share/waves/conf/waves.conf` in `rest_api` section the value of `api_key_hash` parameter:

```
rest-api {
  …
  api_key_hash = “3QbuM9nJP9GZQDekgfGboPGDQe4g1nsH4kmK2jbCLAFJ”
}
```

8. Restart the node by executing

```bash
sudo systemctl restart waves
```

9. Make sure that blockchain is downloaded. Execute

```bash
sudo journalctl -u waves -f
```

As a result, the blockchain download log will be displayed. If "microblock appended" entries started to appear in the log, then blockchain is completely downloaded.

10. Press Ctrl-C to close the log.
11. Discover the node [account address](/blockchain/account/address.md). To do so, execute

```bash
curl 127.0.0.1:6869/addresses
```

As a result, the node account address will be displayed, for example, `3PAbvhnSesJGUd1Ry6YM1qCALTSD4pYGxG`

12. Execute the following steps in `/usr/share/waves/conf/waves.conf` file:

    12.1. Create a `waves.dex` section.

    12.2. Set the node account address for matcher. To do so, assign in `waves.dex` section the value obtained in the previous step to `account` parameter.

```
waves.dex {
  account = "3PAbvhnSesJGUd1Ry6YM1qCALTSD4pYGxG"
  # bind-address = "0.0.0.0" # uncomment this line to accept connections from any host
}
```

Considering other node parameters is out of current article scope. To get more information about node parameters, refer to [Node Configuration](/waves-node/node-configuration.md).

## Installing matcher

1. Download the latest version of `dex_<version>_all.deb` file from [https://github.com/wavesplatform/dex/releases](https://github.com/wavesplatform/dex/releases).
2. Execute the following command in a console

```bash
sudo dpkg -i /path/to/dex_<version>_all.deb
```

3. Restart the node by executing

```bash
sudo systemctl restart waves
```

4. Make sure that matcher is successfully started. To do so, execute

```bash
curl 127.0.0.1:6886/matcher
```

As a result, the matcher account address will be displayed. Congratulations, you've successfully installed the matcher.
