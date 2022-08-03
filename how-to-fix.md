# Возможные ошибки и что делать перед повторным запуском

## conf error

Могут быть два подвида этой ошибки. 

### no credentials 

Надо зайти в firebase console и в коллекцию с соответствующим имененм хоста добавить документ с id `!access` 

Содержимое документа:
```
login : yourLogin
password : yourPassword
```

### credentials are not valid

Имеющиеся в документе `!access` логин и пароль видимо не валидные. Надо их поменять на актуальные. 

## system error

Системная ошибка. Надо разбираться как она произошла и чинить с разработчиками.

## Unhandled exception

Надо анализировать проблему и устранять ее причину. Скорее всего на целевом сервере что-то пошло не так.

# Перезапуск

Надо отправить POST запрос чтобы перезапустить процессинг

`https://us-central1-am-starter.cloudfunctions.net/restartProcessing?host=YOUR_HOST&docId=YOUR_DOC_ID`

