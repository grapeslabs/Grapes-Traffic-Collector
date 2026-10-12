# Grapes Traffic Collector

Программное обеспечение «Grapes Traffic Collector» собирает и учитывает метаданные сетевого трафика без обработки содержания передаваемых сообщений. Правообладатель — ООО «Грейпс Лабс» (ИНН 7816419208, ОГРН 1077847491237).

В состав входят две программы:

- `xdpflowd` снимает трафик с сетевого интерфейса сервера и объединяет пакеты одного соединения IPv4 или IPv6 в одну запись потока;
- `flowcollectord` принимает от сетевого оборудования sFlow v5 (UDP 6343), NetFlow v9 и IPFIX (UDP 2055).

Обе программы передают записи в базу данных ClickHouse. Графический интерфейс отсутствует.

## Документация

- [Инструкция по установке](docs/Инструкция_по_установке_Grapes_Traffic_Collector.pdf)
- [Руководство пользователя](docs/Инструкция_пользователя_Grapes_Traffic_Collector.pdf)
- [Функциональные характеристики](docs/Функциональные_характеристики_ПО_Grapes_Traffic_Collector.pdf)
- [Публичная оферта](docs/Оферта_Grapes_Traffic_Collector.pdf)

Скачивание, установка или запуск программы означают акцепт публичной оферты.

## Установка

Дистрибутив версии 1.0.1 размещён в разделе [Releases](https://github.com/grapeslabs/Grapes-Traffic-Collector/releases/tag/v1.0.1). Получите его и распакуйте в каталог `/opt/GrapesNTA`:

```bash
cd /tmp
curl -LO https://github.com/grapeslabs/Grapes-Traffic-Collector/releases/download/v1.0.1/Grapes-Traffic-Collector-1.0.1-linux-amd64.tar.gz
curl -LO https://github.com/grapeslabs/Grapes-Traffic-Collector/releases/download/v1.0.1/Grapes-Traffic-Collector-1.0.1-linux-amd64.tar.gz.sha256
sha256sum -c Grapes-Traffic-Collector-1.0.1-linux-amd64.tar.gz.sha256
mkdir -p /opt/GrapesNTA
tar -C /opt/GrapesNTA -xzf Grapes-Traffic-Collector-1.0.1-linux-amd64.tar.gz
```

Дальше выполните шаги инструкции по установке начиная с раздела 3 «Настройка конфигурации». Скрипт создания таблиц из приложения к инструкции уже лежит в архиве: `/opt/GrapesNTA/schema/01_flows_raw.sql`.

## Поддержка

По вопросам развёртывания, настройки и работы обращайтесь по адресу info@grapeslabs.ru.
