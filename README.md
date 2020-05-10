
# Freeland Artguard Service

![logo](https://sagleft.ru/projects/freeland/artguard/logo-256.png)

**ArtGuard** - это сервис защиты прав на интеллектуальную собственность, который работает на основе MFCoin Blockchain проекта Freeland.

## Для кого этот сервис

Это сервис для творческих людей, которые хотят закрепить за собой права на свои произведения, но не хотят бумажной волокиты и юридических сложностей.

Достаточно сделать запись в блокчейне с копией (возможно, частичной), описанием произведения, авторства. Эта запись будет доступна публично и любой желающий сможет проверить права на произведение по имени этой записи.

## Техническое описание

Для записи данных в блокчейн используется NVS (Name Value System).
Разберем на примере записи с именем ` art:intersqubrex:1 `:
* `art` - приставка NVS записи, обозначающая категорию;
* `intersqubrex` - название произведения (в данном случае, серии зарисовок);
* `1` - порядковый номерзарисовки (части произведения) (опционально).

Содержание записи:
```
name=unknown
image=image:intersqubrex_1.png
author=sagleft
signature=IAuLfYGNRs28bQZc+uCbwvi7pV/3YAwTo/BomAzFNDMoLbOIE3RauutfN5Z/Z62VEm87fjAzwQcJatctdTBZZJs=
type=sketch
info=изображено, что мозг выпал из комфортной коляски и встретился с безразличной вселенной
```

подробнее про используемые поля:
* `name` - название произведения (или части произведения);
* `image` - ссылка на название записи с файлом. может быть `file` для произвольного типа файла. в данном случае используется сжатый фотоскан;
* `author` - автор произведения. используется имя nvs-записи или MFCoin-адрес автора;
* `signature` - подпись (разберем далее);
* `type` - тип произведения (в данном случе sketch - эскиз, зарисовка);
* `info` - описание произведения, что изображено (в случае рисунка).

Получение `signature`:
подписать сообщение с содержанием:
* имя NVS-записи произведения.
* например, `image:intersqubrex_1.jpg`

подписать адресом:
* указанным в поле `author` - MFCoin-адрес или другая NVS запись, адрес которой использовать.
* например, указанное значение `author` = `sagleft` переводится в MFCoin адрес: `Me8xgLsEWUNaJe9ZMRh79mzsPFhubCLUHK`.

Вы можете проверить подпись этого сообщения:
* адрес: `Me8xgLsEWUNaJe9ZMRh79mzsPFhubCLUHK`
* сообщение: `art:intersqubrex:1`
* подпись:
```
IAuLfYGNRs28bQZc+uCbwvi7pV/3YAwTo/BomAzFNDMoLbOIE3RauutfN5Z/Z62VEm87fjAzwQcJatctdTBZZJs=
```

Записи можно посмотреть через [Block Explorer](https://explorer.mfcoin.net) или через ПК-кошелек.


## Использование вручную

(возможно, позже появится онлайн-утилита для работы с сервисом, пока только описание работы в ручном режиме)

TODO: описание как в ПК-кошельке это все записать.
