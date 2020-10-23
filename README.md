Python FCB Notifier - mirror te

# Приемник сообщение от ПКБ

**Тестовый проект для имитации клиента ПКБ**

## HTTP

### Request

```
POST /endpoint HTTP/1.1
Host: 127.0.0.1:9090
Content-Type: application/json

{
    "code": "<code>",
    "file_url": "<file_url>", 
    "checksum" : "<checksum>"
}
```

### Response

```
Status: 202 Accepted
Content-Type: application/json

{
    "sha256": "<hash-of-message>"
}
```

## Запуск на локальном компьютере программиста организации клиентов ПКБ

Для тестирование программы на своей стороне программисту можно использовать программы http туннелирование вроде https://ngrok.com/, конечно предварительно согласовав в начальством и с департаментом безопасности.

Но имеется также способ заливки программы на внешний деплой сервера вроде heroku.com, но в этом случае вам понадобиться как то отлавливать сообщение ПКБ и обрабатывать их без подвязки к вашей организации.