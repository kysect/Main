# ASP.NET + MediatR

Можно почитать:
- Про медиатор - https://github.com/jbogard/MediatR/wiki
- Написание контроллера с CQRS, MediatR - https://codewithmukesh.com/blog/onion-architecture-in-aspnet-core/

При разработке API мы используем медиатор как альтернативу написания сложных слабосвязанных сервисов. При использовании медиатора всё также проектируются контроллеры и методы в них, но вместе написания под сервисного класса под контроллер, пишутся отдельные хендлеры. В контексте имплементации контроллеров можно выделить такие типы классов:
- Handler - класс, который реализует IRequestHandler и содержит логику обработки запроса
- Команды - это такие хендлеры, которые выполняют какое-то действия. Например, добавление или удаление пользователя. Команда имеет входные параметры и _обычно_ ничего не возвращает.
- Квери - это такие хендлеры, которые запрашивают данные и возвращают. Например, получение юзеров. Такие запросы возвращают информацию.

Можно понять, что такой подход плодит большое количество классов и нужно их аккуратно структурировать. Команды и квери можно группировать по принадлежности к контроллер. Файловая структура:

```
ProjectName.Application/
    FeatureName/
        ScopeName/
            ScopeController.cs
            Queries/
                GetQuery.cs
            Commands/
                CreateCommand.cs
            Dtos/
                SomeArguments.cs
```

Пример метода контроллера:
```cs
[HttpPost]
public async Task<IActionResult> Create([FromBody] CreateStudent.Command command)
{
    await _mediator.Send(command);
    return Ok();
}
```

Пример файла с командой:
```cs
public static class CreateStudent // Container for command and handler
{
    public class Command : IRequest // Command argument
    {
        public string StudentName { get; set; }
    }
    
    public class Handler : IRequestHandler<Command> // Handler
    {
        private readonly DbContext _db;

        public Handler(DbContext db) // Injecting
        {
            _db = db;
        }
        
        public Task<Unit> Handle(Command request, CancellationToken cancellationToken)
        {
            // Your logic here
        }
    }
}
```