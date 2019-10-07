# PyEarths
PyEarths é uma interface Python orientada a objetos para a plataforma blockchain Earths. A biblioteca está sendo desenvolvida pela comunidade e pelo código aberto. 
A documentação e os exemplos mais recentes podem ser encontrados em [Github repository](https://github.com/PyEarths/PyEarths/). 

## Começando

Você pode instalar o PyEarths usando:

    pip install pyearths

## Documentação

A biblioteca utiliza classes para representar várias estruturas de dados do Earths:

- pyearths.Address
- pyearths.Asset
- pyearths.AssetPair
- pyearths.Order

#### Exemplo de código
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



### Código fonte
[PyEarths Github repository](https://github.com/PyEarths/PyEarths/)
