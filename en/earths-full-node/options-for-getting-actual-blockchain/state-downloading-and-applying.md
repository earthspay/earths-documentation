## State Downloading and Applying

In this option, the user needs to download the [_**latest State**_](http://blockchain.earthsnodes.earths.ga) which is _**the blockchain\_last.tar**_ file \(this State is a generated database by the node when it receives blocks\).  
Please note that this file is updated regularly.  Basically the **State** represents a **LevelDB** which stores its files in `/var/lib/earths/data`

### Step-by-Step

The user needs to follow these steps for State downloading and applying:

1. [Download](http://blockchain.earthsnodes.earths.ga) the State database \(the blockchain\_last.tar file\).
2. Run the checksum by some tools in order to checksum of both files in the link above \(the checksum of this file _**blockchain\_last.tar**_ should be the same value which is exist inside this file: _**blockchain\_last.tar.SHA1SUM**_ \).
3. Delete data folder by running `sudo rm -rdf /var/lib/earths/data`
4. Unpack the State to the correct direction `/var/lib/earths/data`  \(note, previously the user needed to clear this folder but not anymore\).
5. Finally, the user starts the node by running `sudo systemctl start earths`

You can download recently exported blockchains using following links:

* TestNet: [http://blockchain.testnet.earthsnodes.earths.ga/](http://blockchain.testnet.earthsnodes.earths.ga/)
* MainNet: [http://blockchain.earthsnodes.earths.ga/](http://blockchain.earthsnodes.earths.ga/)



