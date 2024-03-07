# Получить список добавленных клиентов
Получить список добавленных клиентов. Есть возможность указать параметры сортировки (фильтрации) для детального отображения данных.
```
GET /clients
```
## Описание параметра запроса
|    Наименование    |   Тип   |                    Описание                     |
|:------------------:|:-------:|:-----------------------------------------------:|
|       sortBy       | String  | Название поля, по которому требуется сортировка |
|     sortOrder      | String  |                    asc, desc                    |
| startBirthdayDate  | String  |          Дата рождения, начало периода          |
|  endBirthdayDate   | String  |          Дата рождения, конец периода           |
|     searchText     | String  |                 Значение поиска                 |
|        sex         | String  |                      Пол                        |
|        page        | Integer |                    Страница                     |
|      pageSize      | Integer |        Количество элементов на странице         |

## Ответ от сервера
| Код | Тело ответа                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                  Описание                   |
|:---:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------:|
| 200 | ```{"clientList": [{"id": 3,"firstName": "Bukarev1","lastName": "Daniil1","middleName": "Maksimovich1","sex": "MAN","birthday": "2024-02-26T14:00:12.012+00:00","phoneNumber": "87778886655","active": true,"identifiers": [{"id": 2,"value": "333,333333","identifiersType": {"id": 1,"value": "Карта"}}]},{"id": 6,"firstName": "Bukarev5","lastName": "Daniil5","middleName": "Maksimovic5h","sex": "MAN","birthday": "2024-02-26T14:13:29.696+00:00","phoneNumber": "87778886655","active": true,"identifiers": [{"id": 1,"value": "123.234234","identifiersType": {"id": 1,"value": "Карта"}}]}],"totalCount": 7}``` |  Успешная операция по получению клиентов    |
| 400 | ```{"message": "400 Bad Request","date": "2023-12-18T15:49:42.493Z"}```                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |             Неправильный запрос             |
| 500 | ```{"timestamp": 1426615606,"status": 500,"error": "Internal Server Error","path": "/api-v1","message": "Required String parameter 'name' is not present"}```                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Непредусмотренная внутренняя ошибка сервера |
## Пример запроса
Request URL:
```
http://localhost:9778/api/v1/clients?page=2&pageSize=2
```
curl:
```
curl -X 'GET' \
  'http://localhost:9778/api/v1/clients?page=2&pageSize=2' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhbGciO*********oBgGVTrd7ckM'
```