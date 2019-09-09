# Бинарный формат транзакции лизинга

## Транзакция версии 2

| Порядковый номер поля | Поле | Название JSON-поля |Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Флаг версии | | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Указывает что [версия транзакции](/blockchain/binary-format/transaction-binary-format.md) является второй или выше.<br>Значение должно быть равно 0 |
| 2 | [ID типа транзакции](/blockchain/transaction-type.md) | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 8 |
| 3 | [Версия транзакции](/blockchain/transaction/transaction-version.md) |version| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 2 |
| 4 | Зарезервированное поле |  | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 0 |
| 5 | Открытый ключ аккаунта отправителя транзакции | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 6 | Получатель | recipient | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | [Адрес](/blockchain/address.md) либо псевдоним получателя. <br>Если первый байт поля равен 1, то в поле хранится адрес; если 2 — псевдоним |
| 7 | Количество | amount | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Количество токенов, отдаваемых в лизинг |
| 8 | Комиссия| fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Комиссия за транзакцию в [WAVELET](/blockchain/token/wavelet.md) |
| 9 | Временная метка | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Unix-время отправки транзакции в блокчейн |
| 10 | Подтверждения |proofs| Массив [подтверждений](/blockchain/transaction/transaction-proof.md) | `S` | Если массив пустой, то `S`= 3. <br>Если массив не пустой, то `S`= 3 + 2 × `N` + \(`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>\), <br>где <br>`N` — количество подтверждений в массиве, <br>`P`<sub>n</sub> — размер `N`-го подтверждения в байтах.<br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |

## JSON-представление транзакции бинарного формата версии 2

```json
{
   "type":8,
   "version":2,
   "senderPublicKey":"GNswAY61mER5ZyUFeDBo1UyKGkPSSmmnd6yj7axN2n8f",
   "recipient":"3PMWRsRDy882VR2viKPrXhtjAQx7ygQcnea",
   "amount":14000000000,
   "fee":100000,
   "feeAssetId":null,
   "timestamp":1548660916755,
   "proofs":[
      "2opTj7mGKXLRajkJ78wN4ctSWqTeWtvisHaR8BnL2amqJ2KB313BbcpDYJKcqr7o7EpYjL5tppMz2pGjUMWbJe9b"
   ],
   "id":"J6jZCzLpWJX8EDVhopKFx1mcbFizLGHVb44dvqPzH4QS",
   "sender":"3PMYNm8hshzCNjZ8GpPta5SyN7qBTEzS7Kw",
   "status":"canceled",
   "height":1370973
}
```

## Бинарный формат версии 1

| Порядковый номер поля | Название поля | Тип поля | Размер поля в байтах | Описание поля |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Тип транзакции | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | ID типа транзакции. <br>Значение должно быть равно 8 |
| 2 | Публичный ключ отправителя | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | Публичный ключ аккаунта отправителя |
| 3 | Получатель  | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | Адрес либо псевдоним получателя. <br>Если первый байт поля равен 1, то в поле хранится адрес; если 2 — псевдоним |
| 4 | Количество | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Количество токенов, отдаваемых в лизинг |
| 5 | Комиссия | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Комиссия за транзакцию в WAVELET |
| 6 | Временная метка | [Long](/blockchain/blockchain/blockchain-data-types.md)| 8 | Unix-время публикации транзакции в сеть |
| 7 | Подпись | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) |
