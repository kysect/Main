# Swagger codegen
## Swaggr in a nutshell

- Swagger (OpenAPI) — это не зависящая от языка спецификация для описания REST API. Она позволяет компьютерам и пользователям лучше понять возможности REST API без прямого доступа к исходному коду
- Swagger UI - инструмент, который позволяет визуализировать спецификацию. Его можно разместить в ASP и получить возможность через него также вызывать существующие методы API.

Почитать можно тут - https://docs.microsoft.com/ru-ru/aspnet/core/tutorials/web-api-help-pages-using-swagger.

## Client generation

С использованием Swagger'а появляется возможность генерировать шаблонные клиенты для API. Один из вариантов - это использовать NSwagStudio. Важно понимать, что генерируется клиент по написанным контроллерам и DTO. При их смене нужно перегенерировать клиент.

Процесс обновления:
1. Запустить [NSwagStudio](https://github.com/RicoSuter/NSwag/wiki/NSwagStudio)
2. Открыть в ней файл *.nswag, он обычно находится в проекте SDK.
3. **Запустить бек** и посмотреть на каком порте он запустился
4. Во вкладке "OpenApi/Swagger Specification" удостовериться, что в поле "Specification URL" введена ссылка с правильным портом и нажать Create local copy

![](https://i.imgur.com/U3kCVIp.png)

5. Удостовериться, что в "Outputs" выбран только "CSharp Client", после чего нажать "Generate Files"
6. Нажать Ctrl+S что бы сохранить обновлённый nswag файл

## Возможные ошибки

* **An error occured while sending the request** - Либо бек не запущен, либо введена неправильная Specification URL ![](https://i.imgur.com/VYfHDqG.png)
