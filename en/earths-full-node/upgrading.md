# Upgrading

1. First of all, you need to check the[ latest Earths Release.](https://github.com/earthspay/Earths/releases) and choose the latest Mainnet release.
2. Download the DEB or Jar file depending on your operating system.
3. Upgrade DEB by running the following command:
   ```bash
   sudo dpkg -i earths_X.Y.Z_all.deb
   ```
4. Or upgrade JAR by copying the new version over the old one
5. Check the release notes. If there are new features to vote and activate, you will need to include that in the config.

## Upgrading the Node

Basically, the node should be upgraded as follows:  
1. Stop the node  
2. Export all existing blocks in the blockchain to a binary file. Please read the documentation about [_**export and import of the blockchain**_](/earths-full-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.md) or [_**download the binary file**_](/earths-full-node/options-for-getting-actual-blockchain/state-downloading-and-applying.md).  
3. Update node's executables  
4. Import binary file  
5. Start the node

## Upgrading the Node to the Latest Version on Linux

1. Stop the Node by executing the following command:
   ```bash
   sudo systemctl stop earths
   ```
2. After stopping the node execute following command to [export existing blocks to a binary file](/earths-full-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.md):
   ```bash
   sudo -u earths exporter /etc/earths/earths.conf [output-file-name] [height]
   ```
3. Remove data folder:
   ```bash
   sudo rm -rdf /var/lib/earths/data
   ```
4. Install the new version of the node:
   ```bash
   sudo dpkg -i earths_X.Y.Z_all.deb
   ```
5. [Import blocks from the binary file](/earths-full-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.md):
   ```bash
   sudo -u earths importer /etc/earths/earths.conf [binary-file-name]
   ```
6. After import start the node:
   ```bash
   sudo systemctl start earths
   ```

## Update the Configuration

Please, read the updated documentation of [_**Earths node configuration file**_](/earths-full-node/configuration-parameters.md)_**.**_

