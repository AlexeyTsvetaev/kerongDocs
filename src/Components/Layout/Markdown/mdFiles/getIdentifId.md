# Получить идентификатор по его Id
Получить идентификатор по его Id
```
GET /identifiers/{id}
```
## Описание переменной параметра запроса
| Наименование |   Тип   |      Описание     |
|:------------:|:-------:|:-----------------:|
|     id       | Integer | Id идентификатора |

## Ответ от сервера
| Код | Тело ответа                                                                                                                                                   |                       Описание                       |
|:---:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------:|
| 200 | ```{"id": 1,"value": "123,14325","identifiersType": {"id": 1,"value": "Карта"}}```                                                                            | Успешная операция по получению идентификатора |
| 400 | ```{"message": "400 Bad Request","date": "2023-12-18T15:49:42.493Z"}```                                                                                       |                 Неправильный запрос                  |
| 500 | ```{"timestamp": 1426615606,"status": 500,"error": "Internal Server Error","path": "/api-v1","message": "Required String parameter 'name' is not present"}``` |     Непредусмотренная внутренняя ошибка сервера      |
## Пример запроса
Request URL:
```
http://localhost:9778/api/v1/identifiers/1
```
curl:
```
curl -X 'GET' \
  'http://localhost:9778/api/v1/identifiers/1' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhb******IcYSRikXTE9s'
```