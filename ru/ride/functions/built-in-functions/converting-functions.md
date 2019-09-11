# Функции конвертации

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [addressFromPublicKey(ByteVector): Address](#address-from-public-key) | Получает [адрес](/blockchain/address.md), соответствующий открытому ключу аккаунта | 82 |
| 2 | [addressFromRecipient(Address&#124;Alias): Address](#address-from-recipient) | Получает [адрес](/blockchain/address.md), соответствующий [псевдониму](/blockchain/account/alias.md) | 100 |
| 3 | [parseInt(String): Int&#124;Unit](#parse-int) | Конвертирует строковое представление числа в эквивалентное целое число | 20 |
| 4 | [parseIntValue(String): Int](#parse-int-value) | Конвертирует строковое представление числа в эквивалентное целое число.<br>Выбрасывает исключение, если строка не может быть спарсена | 20 |
| 5 | [toBytes(Boolean): ByteVector](#to-bytes-boolean) | Конвертирует логическое значение в массив байтов | 1 |
| 6 | [toBytes(Int): ByteVector](#to-bytes-int) | Конвертирует целое число в массив байтов | 1 |
| 7 | [toBytes(String): ByteVector](#to-bytes-string) | Конвертирует строку в массив байтов | 1 |
| 8 | [toInt(ByteVector): Int](#to-int-bytevector) | Конвертирует массив байтов в целое число | 10 |
| 9 | [toInt(ByteVector, Int): Int](#to-int-bytevector-int) | Конвертирует массив байтов начиная с указанного индекса в целое число | 10 |
| 10 | [toString(Address): String](#to-string-address) | Конвертирует массив байтов [адреса](/blockchain/address.md) в строку | 10 |
| 11 | [toString(Boolean): String](#to-string-boolean) | Конвертирует логическое значение в строку | 1 |
| 12 | [toString(Int): String](#to-string-int) | Конвертирует целое число в строку | 1 |
| 13 | [toUtf8String(ByteVector): String](#to-utf8-string-bytevector) | Конвертирует массив байтов в строку в [UTF-8](https://ru.wikipedia.org/wiki/UTF-8) | 20 |

## addressFromPublicKey(ByteVector): Address<a id="address-from-public-key"></a>

Получает [адрес](/blockchain/address.md), соответствующий открытому ключу аккаунта.

``` ride
addressFromPublicKey(publicKey: ByteVector): Address
```

### Параметры

#### `publicKey`: ByteVector

Открытый ключ для конвертации.

### Примеры

``` ride
let publicKey = base58'J1t6NBs5Hd588Dn7mAPytqkhgeBshzv3zecScfFJWE2D'
let add = addressFromPublicKey(publicKey)# The result will be the address for the defined public key which is '3NADPfTVhGvVvvRZuqQjhSU4trVqYHwnqjF'
```

## addressFromRecipient(Address&#124;Alias): Address<a id="address-from-recipient"></a>

Получает [адрес](/blockchain/address.md), соответствующий [псевдониму](/blockchain/account/alias.md).

``` ride
addressFromRecipient(AddressOrAlias: Address|Alias): Address
```

### Параметры

#### `AddressOrAlias`: Address&#124;Alias

Адрес или псевдоним, обычно получателя транзакции.

## parseInt(String): Int&#124;Unit<a id="parse-int"></a>

Конвертирует строковое представление числа в эквивалентное целое число.

``` ride
parseInt(str: String): Int|Unit
```

### Параметры

#### `str`: String

Строка для конвертации.

### Примеры

``` ride
let str = "Waves"
let result = parseInt(str)
```

## parseIntValue(String): Int<a id="parse-int-value"></a>

Конвертирует строковое представление числа в эквивалентное целое число.

Выбрасывает исключение, если строка не может быть сконвертирована.

``` ride
parseIntValue(str: String): Int
```

### Параметры

#### `str`: String

Строка для конвертации.

### Примеры

``` ride
let str = "Waves"
let result = parseIntValue(str)
```

## toBytes(Boolean): ByteVector<a id="to-bytes-boolean"></a>

Конвертирует логическое значение в массив байтов.

``` ride
toBytes(b: Boolean): ByteVector
```

### Параметры

#### `b`: Boolean

Логическое значение для конвертации.

### Примеры

``` ride
let b = true
let result = toBytes(b)
```

## toBytes(Int): ByteVector<a id="to-bytes-int"></a>

Конвертирует целое число в массив байтов.

``` ride
toBytes(n: Int): ByteVector
```

### Параметры

#### `n`: Int

Целое число для конвертации.

### Примеры

``` ride
let n = 100
let result = toBytes(n)
```

## toBytes(String): ByteVector<a id="to-bytes-string"></a>

Конвертирует строку в массив байтов.

``` ride
toBytes(s: String): ByteVector
```

### Параметры

#### `s`: String

Строка для конвертации.

### Примеры

``` ride
let s = "Waves"
let result = toBytes(s)
```

## toInt(ByteVector): Int<a id="to-int-bytevector"></a>

Конвертирует массив байтов в целое число.

``` ride
toInt(bin: ByteVector): Int
```

### Параметры

#### `bin`: ByteVector

Массив байтов для конвертации.

### Примеры

``` ride
let bin = base58'abcd'
let result = toInt(bin)
```

## toInt(ByteVector, Int): Int<a id="to-int-bytevector-int"></a>

Конвертирует массив байтов начиная с указанного индекса в целое число.

``` ride
toInt(bin: ByteVector, offset: Int): Int
```

### Параметры

#### `bin`: ByteVector

Массив байтов для конвертации.

#### `offset`: Int

Индекс.

### Примеры

``` ride
let bin = base58'abcd'
let result = toInt(bin,2)
```

## toString(Address): String<a id="to-string-address"></a>

Конвертирует массив байтов [адреса](/blockchain/address.md) в строку.

``` ride
toString(Address: Address): String
```

### Параметры

#### `Address`: Address

Адрес для конвертации.

## toString(Boolean): String<a id="to-string-boolean"></a>

Конвертирует логическое значение в строку.

``` ride
toString(b: Boolean): String
```

### Параметры

#### `b`: Boolean

Логическое значение для конвертации.

### Примеры

``` ride
let b = true
let result = toString(b)
```

## toString(Int): String<a id="to-string-int"></a>

Конвертирует целое число в строку.

``` ride
toString(n: Int): String
```

### Параметры

#### `n`: Int

Целое число для конвертации.

### Примеры

``` ride
let n = 100
let result = toString(n)
```

## toUtf8String(ByteVector): String<a id="to-utf8-string-bytevector"></a>

Конвертирует массив байтов в строку в [UTF-8](https://ru.wikipedia.org/wiki/UTF-8).

``` ride
toUtf8String(u: ByteVector): String
```

### Параметры

#### `u`: ByteVector

Массив байтов для конвертации.

### Примеры

``` ride
let u = base58'abcd'
let result = toUtf8String(u)
```
