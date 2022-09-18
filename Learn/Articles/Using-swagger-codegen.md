# Swagger codegen

## Swaggr in a nutshell

- Swagger (OpenAPI) — это не зависящая от языка спецификация для описания REST API. Она позволяет компьютерам и пользователям лучше понять возможности REST API без прямого доступа к исходному коду
- Swagger UI - инструмент, который позволяет визуализировать спецификацию. Его можно разместить в ASP и получить возможность через него также вызывать существующие методы API.

Почитать можно тут - https://docs.microsoft.com/ru-ru/aspnet/core/tutorials/web-api-help-pages-using-swagger.

## Client generation

С использованием Swagger'а появляется возможность генерировать шаблонные клиенты для API. Один из вариантов - это использовать NSwagStudio. Важно понимать, что генерируется клиент по написанным контроллерам и DTO. При их смене нужно перегенерировать клиент.

### Процесс создания

1. Запустить [NSwagStudio](https://github.com/RicoSuter/NSwag/wiki/NSwagStudio)
2. Создать новый *\*.nswag* файл (File > New)
3. Выбрать нужный нам тип клиента (В дальнейшем тексте будет использоваться CSharp Client, так что некоторые пункты могут быть не актуальны для TypeScript)

![](https://i.imgur.com/n1qp8T1.png)

4. В настройках указать нужный нам Namespace и в самом низу в разделе Output указать путь, куда будет генерироваться клиент
5. По остальным настройкам: можно изучить самостоятельно и выбрать подходящие вам, большинство варьируется от ваших потребностей и предпочтений. Пример настройки можно посмотреть, открыв [этот](https://github.com/kysect/iwentys/blob/master/Source/Endpoints/Iwentys.Endpoints.Sdk/IwentysApiClient.nswag) файл в NSwagStudio
6. **Запустить бек** и посмотреть на каком порте он запустился
7. Во вкладке "OpenApi/Swagger Specification" в поле "Specification URL" ввести ссылку на спецификацию, она будет выглядеть примерно так ```https://localhost:44388/swagger/v1/swagger.json```
8. Нажать "Create local" copy
9. Нажать "Generate Files", после чего по указанному ранее пути создастся клиент
10. Нажать Ctrl+S что бы сохранить nswag файл с конфигурацией клиента, в дальнейшем нужно будет просто обновлять его и перегенерировать клиент

### Процесс обновления:

1. Запустить [NSwagStudio](https://github.com/RicoSuter/NSwag/wiki/NSwagStudio)
2. Открыть в ней файл *\*.nswag*, он обычно находится в проекте SDK.
3. **Запустить бек** и посмотреть на каком порте он запустился
4. Во вкладке "OpenApi/Swagger Specification" удостовериться, что в поле "Specification URL" введена ссылка с правильным портом и нажать Create local copy

![](https://i.imgur.com/U3kCVIp.png)

5. Удостовериться, что в "Outputs" выбран нужный тип клиента ("CSharp Client"), после чего нажать "Generate Files"
6. Нажать Ctrl+S что бы сохранить обновлённый nswag файл


### Как этим вообще пользоваться

Достаточно просто: создаём сгенерированный класс Client руками или череез DI контейнер. У него есть единственная зависимость - HttpClient. У HttpClient обязательно должно быть установлено поле BaseAddress - собственно адрес нашего сервера. В случае веб клиента его можно получить из класса ASP

<p>

```c#
new HttpClient { BaseAddress = new Uri(builder.HostEnvironment.BaseAddress) }
```

</p>

Также его можно установить просто строкой. Итоговое создание клиента будет выглядеть примерно так:

DI:

<p>

```c#
builder.Services.AddScoped(_ => new HttpClient { BaseAddress = new Uri(builder.HostEnvironment.BaseAddress) });
builder.Services.AddScoped<Client>();
```

</p>

Ручками:

<p>

```c#
var client = new Client(new HttpClient(){BaseAddress = new Uri("https://localhost:5001/")});
```

Класс Client по сути дублирует методы нашего API, так что дальше можно просто вызывать нужные нам методы

</p>

</details>

## Возможные ошибки

* **An error occured while sending the request** - Либо бек не запущен, либо введена неправильная Specification URL ![](https://i.imgur.com/VYfHDqG.png)
