# Starting new repository

Экосистема dotnet позволят очень легко создавать новые проекты и начинать писать код. Но со временем появляется всё больше нюансов, которые нужно не забывать во время старта очередного проекта.

Чек лист:

- Создать репозиторий в организации Kysect;
- Склонировать репозиторий и создать в нём директорию `Source`;
- В директории Source создать Blank solution с названием `Kysect.*RepositoryName*` (т.е. добавить префикс `Kysect.` к названию репозитория);
- Скопировать актуальный .editorconfig с https://github.com/Kysect/CodeRules/ в директорию Source и добавить файл в sln;
- Добавить в корень репозитория директорию `.github/workflows` и создать в ней конфигурацию для Github Action CI для запуска билда и тестов солюшена на пул реквестах;
- Убедиться, что в корне репозитоиря лежит `.gitignore` для Visual studio и добавить его, если нет;
- Добавить в созданные csproj конфигурацию для анализа - `<EnforceCodeStyleInBuild>True</EnforceCodeStyleInBuild>` и `<TreatWarningsAsErrors>True</TreatWarningsAsErrors>`;
- Завести ишую на подключение SonarCloud анализа для репозитория;
- Описать в `Readme.md` проект, его цель и особенности.
