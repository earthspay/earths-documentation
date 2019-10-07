# EarthsCS
A C# library for interacting with the Earths blockchain

Supports node interaction, offline transaction signing, Matcher orders, and creating addresses and keys.

## Getting Started

You can download **EarthsCS.dll** from [releases](https://github.com/earthspay/EarthsCS/releases) and add it to your project's References and in your code as:
```
using EarthsCS;
```

If you want to work with full EarthsCS project as contributor you should use also all crypto **.dll** from releases in your References.

Target framework .NET Framework 4.5.1
## Documentation

The library utilizes classes to represent various Earths data structures and encoding and serialization methods:

- EarthsCS.Node
- EarthsCS.Order
- EarthsCS.OrderBook
- EarthsCS.PrivateKeyAccount
- EarthsCS.Transaction
- EarthsCS.AddressEncoding
- EarthsCS.Base58
- EarthsCS.Utils


#### Code Example
Code examples are in [EarthsCSTests](https://github.com/earthspay/EarthsCS/tree/master/EarthsCSTests) project.

### Source code
[EarthsCS Github repository](https://github.com/earthspay/EarthsCS)
