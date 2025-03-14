# pymongo-api

## Как запустить

Условия:
1. на машине должны быть установлены Docker и Docker Compose
2. доступны ресурсы машины

1. Запустить mongodb и приложение(здесь же происходит заполнение бд):

```shell
docker compose up --build -d
```

2. дождаться подьема контейнеров

## Как проверить

### Если вы запускаете проект на локальной машине

Откройте в браузере http://localhost:8080

### Если вы запускаете проект на предоставленной виртуальной машине

Узнать белый ip виртуальной машины

```shell
curl --silent http://ifconfig.me
```

Откройте в браузере http://<ip виртуальной машины>:8080

## Доступные эндпоинты

Список доступных эндпоинтов, swagger http://<ip виртуальной машины>:8080/docs

## Как остановить

```shell
docker compose down
```

## Вспомогательные команды

1. проверить количество документов через терминал
```shell
docker compose exec -T mongos-router0 mongosh --quiet --port 27017 <<EOF
use somedb
db.helloDoc.countDocuments()
EOF
```
