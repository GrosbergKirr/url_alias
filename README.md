# gRPC Сервер для работы с  URL

Данный gRPC сервер предоставляет сервис для создания, хранения и получения алиасов к URL.

## Установка и Запуск

1. `docker-compose -f ./Docker/docker-compose.yml build`
2. `docker-compose -f ./Docker/docker-compose.yml up -d`

## Использование

### 1. Эндпоинт для получения укороченной ссылки


```proto
service Api {
   rpc ChangeURL(URLRequest) returns (URLResponse);
}

message URLRequest {
   string URL = 1;
}

message URLResponse {
   string URL = 1;
   string Error = 2;
}
```
### 2. Эндпоинт для получения полной ссылки
```proto
service Api {
   rpc GetSourceURL(URLRequest) returns (URLResponse);
}

message URLRequest {
   string URL = 1;
}

message URLResponse {
   string URL = 1;
   string Error = 2;
}
```

