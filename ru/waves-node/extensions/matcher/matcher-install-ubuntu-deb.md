# Установка матчера на Ubuntu из deb-пакета

## Системные требования

- Двухъядерный процессор
- 4 Гбайт оперативной памяти
- Жесткий диск объёмом 50 Гбайт

## Проверка наличия OpenJDK версии 8

Убедитесь, что на вашем компьютере установлен OpenJDK версии 8. Для этого выполните в консоли команду

```bash
java -version 2>&1 | grep “openjdk version \“1.8” | wc -l
```

Если в консоль выводится `0`, перейдите к шагу Установка OpenJDK версии 8.

Если в консоль выводится `1`, перейдите к шагу Установка ноды.

## Установка OpenJDK версии 8

Для установки OpenJDK версии 8 выполните в консоли команды

```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre
```

## Установка ноды

1. Скачайте последнюю версию файла `waves_<версия>_all.deb` со страницы [https://github.com/wavesplatform/Waves/releases](https://github.com/wavesplatform/Waves/releases).
2. Выполните в консоли команду

```bash
sudo dpkg -i /путь/к/файлу/waves_<версия>_all.deb
```

3. Перейдите в папку `/var/lib/waves`, выполнив команду

```bash
cd /var/lib/waves
```

## Настройка ноды

1. Откройте файл `/usr/share/waves/conf/waves.conf` при помощи команды `sudo nano /usr/share/waves/conf/waves.conf`
2. Решите, следует ли использовать вновь созданный или существующий аккаунт для [ноды](/blockchain/node.md). Использовать существующий аккаунт может понадобиться в том случае, если вы планируете сделать свою ноду [майнящей](/blockchain/node/mining-node.md).

- Чтобы использовать вновь созданный аккаунт, раскомментируйте в секции `wallet` параметр `password` и задайте ему значение. Пример:

```
wallet {
  # Password to protect wallet file
  password = iAmGoingToUseAnewAccount
  # Wallet seed as BASE58 string
  # seed =
}
```

- Чтобы использовать существующий аккаунт, укажите в секции `wallet` пароль и, в кодировке base58, seed.

```
wallet {
  # Password to protect wallet file
  password = iAmGoingToUseAnExistingAccount
  # Wallet seed as BASE58 string
  seed = 35S7EzKMHMN4JQyWnwpp84Zot1yqLoP2Q46RsbYRzgFq7n8AiV8L6skeGPq93P2NU4pGcZFeNTAT2TKJTa2XvqRwSdCmBR556MBmtZ3ggAkBtd3CCZFvZwZufz1ZqfzJQ
}
```

3. Добавьте в файл `/usr/share/waves/conf/waves.conf` секцию

```
waves.extensions = ["com.wavesplatform.dex.Matcher"]
```

4. Задайте в файле `/usr/share/waves/conf/waves.conf` в секции `rest_api` значения следующих параметров:
- `enable = yes`
- `api_key_hash = “”`

```
rest-api {
  # Disable node’s REST API
  enable = yes
  …
  api_key_hash = “”
}
```

5. Запустите ноду, выполнив в консоли команду

```bash
sudo systemctl start waves
```

6. Сформируйте значение `api_key_hash`, отличающееся от пустой строки. Для этого выполните команду

```bash
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '<YOUR_ARBITRARY_STRING>' '127.0.0.1:6869/utils/hash/secure'
```

Вместо `<YOUR_ARBITRARY_STRING>` используйте собственное значение (рекомендуется запомнить его). В результате будет выведено сообщение вида

```
{"message": "YOUR_ARBITRARY_STRING", "hash": "3QbuM9nJP9GZQDekgfGboPGDQe4g1nsH4kmK2jbCLAFJ"}
```

7. Задайте в файле `/usr/share/waves/conf/waves.conf` в секции `rest_api` значение параметра `api_key_hash`:

```
rest-api {
  …
  api_key_hash = “3QbuM9nJP9GZQDekgfGboPGDQe4g1nsH4kmK2jbCLAFJ”
}
```

8. Перезагрузите ноду командой

```bash
sudo systemctl restart waves
```

9. Дождитесь завершения скачивания блокчейна. Выполните в консоли команду

```bash
sudo journalctl -u waves -f
```

В результате будет отображён журнал скачивания блокчейна. Появление в журнале записей "microblock appended" означает, что блокчейн полностью скачан.

10. Нажмите Ctrl-C чтобы закрыть журнал.
11. Узнайте адрес аккаунта ноды. Для этого выполните в консоли команду

```bash
curl 127.0.0.1:6869/addresses
```

В результате в консоли отобразится адрес аккаунта ноды вида `3PAbvhnSesJGUd1Ry6YM1qCALTSD4pYGxG`

12. Выполните следующие действия в файле `/usr/share/waves/conf/waves.conf`:

    12.1. Создайте секцию `waves.dex`
    
    12.2. Укажите адрес аккаунта ноды для матчера. Для этого в секции `waves.dex` присвойте параметру `account` полученное на предыдущем шаге значение.

```
waves.dex {
  account = "3PAbvhnSesJGUd1Ry6YM1qCALTSD4pYGxG"
  # bind-address = "0.0.0.0" # uncomment this line to accept connections from any host
}
```

Рассмотрение прочих параметров ноды выходит за рамки настоящей статьи. Более подробно параметры ноды рассматриваются в статье [Node Configuration](/waves-node/node-configuration.md).

## Установка матчера

1. Скачайте последнюю версию файла `dex_<версия>_all.deb` со страницы [https://github.com/wavesplatform/dex/releases](https://github.com/wavesplatform/dex/releases).
2. Выполните в консоли команду

```bash
sudo dpkg -i /путь/к/файлу/dex_<версия>_all.deb
```

3. Перезапустите ноду. Для этого выполните команду

```bash
sudo systemctl restart waves
```

4. Убедитесь, что матчер успешно запущен. Для этого выполните команду

```bash
curl 127.0.0.1:6886/matcher
```

В ответ должен быть выведен адрес аккаунта матчера. Если это так, то матчер успешно установлен.