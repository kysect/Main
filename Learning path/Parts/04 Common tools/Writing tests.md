# Тесты

> TODO: I1

## Теория. Виды тестирования, место тестирования в разработке

- Про тестирование на уровне кода и про тестирование как процесс.

## Подготовка среды

Чтобы написать тесты к выполненной работе, необходимо создать тестовый проект и назвать его `ИмяПроектаСРаботой.Tests`. QuickStart'ы по созданию нужного проекта описаны здесь:

- для VisualStudio: [https://docs.microsoft.com/ru-ru/visualstudio/test/getting-started-with-unit-testing](https://docs.microsoft.com/ru-ru/visualstudio/test/getting-started-with-unit-testing?view=vs-2019&tabs=mstest) (выбирайте NUnit)
- для Rider: [https://www.jetbrains.com/help/rider/Getting_Started_with_Unit_Testing.html](https://www.jetbrains.com/help/rider/Getting_Started_with_Unit_Testing.html)

Документация по NUnit доступна по ссылке: [https://docs.nunit.org/articles/nunit/intro.html](https://docs.nunit.org/articles/nunit/intro.html)

## Тестовый класс

Для того, чтобы было, где тестировать, необходимо создать обычный класс и наделить его атрибутом `TestFixture`:

```csharp
namespace Lab1.Tests
{
  [TestFixture]
  public class SomeLogicTests
  {
    ...
  }
}
```

## Тестовые методы

### Атрибуты

Чтобы пометить метод как тестовый, необходимо пометить его атрибутом `Test`:

```csharp
namespace Lab1.Tests
{
  [TestFixture]
  public class SomeLogicTests
  {
		[Test]
		public void SomeTestCase_SomeExpectedBehavior()
		{
			// Some body (once told me...)
		}
  }
}
```

В документации описано ещё множество атрибутов, с ними вы можете ознакомиться сами, однако стараться использовать как можно больше из них не стоит, если в этом нет явной и обоснованной необходимости. Одним из распространённых атрибутов помимо вышеуказанного является атрибут `TestCase`. Если тестовый метод должен принимать какие-то параметры, то следует пометить его этим атрибутом и указать значения параметров, с которыми будет запускаться тестовый метод:

```csharp
namespace Lab1.Tests
{
  [TestFixture]
  public class SomeLogicTests
  {
		[TestCase(0)]
		[TestCase(100000)]
		[TestCase(-1)]
		public void SomeTestCase_SomeExpectedBehavior(int someParameter)
		{
			// Some body (once told me...)
		}
  }
}
```

### Нейминг

Правила именования тестовых методов носят определённый характер.

> Тесты не просто проверяют работоспособность кода — они также предоставляют документацию. Просто посмотрев на набор модульных тестов, вы должны определить поведение кода, не глядя на сам код. Кроме того, если тест не пройден, вы сразу увидите, какие сценарии не соответствуют вашим ожиданиям.

Источник: [https://docs.microsoft.com/ru-ru/dotnet/core/testing/unit-testing-best-practices#naming-your-tests](https://docs.microsoft.com/ru-ru/dotnet/core/testing/unit-testing-best-practices#naming-your-tests)


Имя теста должно состоять из трёх частей:

- имя тестируемого метода
- сценарий, в котором выполняется тестирование
- ожидаемое поведение при вызове сценария

### Тестирование

Проверка результатов выполнения тестируемого метода в основном осуществляется с помощью статических методов класса `Assert` ([https://docs.microsoft.com/en-us/dotnet/api/nunit.framework.assert](https://docs.microsoft.com/en-us/dotnet/api/nunit.framework.assert?view=xamarin-ios-sdk-12))

## Советы по написанию тестов

- Тесты в которых понятно откуда летит ошибки и что именно мы проверяем

## TDD

## Fakes, Mocks and Stubs