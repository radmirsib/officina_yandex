# GeoNames 

# Заказчик: Карьерный центр Яндекс Практикума 

## Цель исследования:

Cопоставление гео-названий с унифицированными именами GeoNames для внутреннего использования Карьерным центром Яндекс Практикума.

## Задачи:

- Создать решение для подбора наиболее подходящих названий с GeoNames. Например, Ереван -> Yerevan.
  
- На примере РФ и стран наиболее популярных для релокации - Беларусь, Армения, Казахстан, Кыргызстан, Турция, Сербия. Города с населением от 15000 человек (с возможностью масштабирования на сервере заказчика).
  
- Возвращаемые поля geonameid, name, region, country, cosine similarity.
  
- Формат данных на выходе: список словарей, например [{dict_1}, {dict_2}, …. {dict_n}] где словарь - одна запись с указанными полями.

## Исходные данные

Используемые таблицы [GeoNames](https://download.geonames.org/export/dump/) и их описание:

- cities15000.txt - all cities with a population > 15000 or capitals (ca 25.000), see 'geoname' table for columns

- admin1CodesASCII.txt - names in English for admin divisions. Columns: code, name, name ascii, geonameid

- alternateNamesV2.zip - alternate names with language codes and geonameId, file with iso language codes, with new columns from and to

- countryInfo.txt - country information : iso codes, fips codes, languages, capital ,...

- geo_test.csv - to check the operation of our model

## Итог исследования:

Были выбрали две многоязыковые модели для использования: `stsb-roberta-large` и `LaBSE`. Расчёт модели не был продолжен, так требовал достаточно продолжительного времени. Тем не менее, была выстроена логическая цепочка операций до конечного расчета, что позволяет увидеть саму структуру проекта.

## Стек технологий:

PostgreSQL, Python, Pandas, NLP, Transformers

## Статус проекта:

Завершен.

