# PyEarths
PyEarths is an object-oriented Python interface to the Earths blockchain platform. The library is developing by community and open source. Latest documentation and examples can be found in [Github repository](https://github.com/PyEarths/PyEarths/). 

## Getting Started

You can install PyEarths using:

    pip install pyearths

## Documentation

The library utilizes classes to represent various Earths data structures:

- pyearths.Address
- pyearths.Asset
- pyearths.AssetPair
- pyearths.Order

#### Code Example
```python
import pyearths as pw

myAddress = pw.Address(privateKey='CtMQWJZqfc7PRzSWiMKaGmWFm4q2VN5fMcYyKDBPDx6S')
otherAddress = pw.Address('3PNTcNiUzppQXDL9RZrK3BcftbujiFqrAfM')
myAddress.sendEarths(otherAddress, 10000000)
myToken = myAddress.issueAsset('Token1', 'My Token', 1000, 0)
while not myToken.status():
	pass
myAddress.sendAsset(otherAddress, myToken, 50)

```



### Source code
[PyEarths Github repository](https://github.com/PyEarths/PyEarths/)