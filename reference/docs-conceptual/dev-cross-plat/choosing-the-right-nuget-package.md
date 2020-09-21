---
title: Выбор подходящего пакета NuGet PowerShell для проекта .NET
description: Наряду с исполняемыми пакетами, опубликованными в каждом выпуске PowerShell, группа разработчиков PowerShell также предоставляет несколько пакетов, доступных в NuGet. Эти пакеты позволяют ориентироваться на PowerShell как платформу API в .NET.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 39369ed872faa76ad2c41d813da5e0a98cf1c078
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85795320"
---
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a>Выбор подходящего пакета NuGet PowerShell для проекта .NET

Наряду с исполняемыми пакетами `pwsh`, опубликованными в каждом выпуске PowerShell, группа разработчиков PowerShell также предоставляет несколько пакетов, доступных в [NuGet][]. Эти пакеты позволяют ориентироваться на PowerShell как платформу API в .NET.

Как приложение .NET, которое предоставляет API и ожидает загрузки библиотек .NET, реализуя собственные двоичные модули, PowerShell должен быть доступен в виде пакета NuGet.

В настоящее время существует несколько пакетов NuGet, которые обеспечивают некоторое представление контактной зоны API PowerShell. Не всегда ясно, какой пакет использовать с определенным проектом. В этой статье рассказывается о нескольких распространенных сценариях для проектов .NET, предназначенных для PowerShell, и о том, как выбрать подходящий пакет NuGet для проекта .NET, ориентированного на PowerShell.

## <a name="hosting-vs-referencing"></a>Размещение и ссылки

В некоторых проектах .NET разработчики пишут код для загрузки в уже существующую среду выполнения PowerShell (например, `pwsh`, `powershell.exe`, интегрированная консоль PowerShell или ISE), а некоторые проекты запускаются в PowerShell в виде отдельных приложений.

- **Ссылка** используется в случаях, когда проект (обычно это модуль) должен загружаться в PowerShell.
  Его необходимо скомпилировать с помощью API, предоставляемых PowerShell, чтобы с ним можно было взаимодействовать, но реализация PowerShell предоставляется процессом PowerShell, который загружает проект. Для ссылки проект может использовать [базовые сборки][] или фактические сборки среды выполнения в качестве целевого объекта компиляции, но он не должен публиковать их в своей сборке.
- **Размещение** используется, когда проекту нужна собственная реализация PowerShell (обычно если это отдельное приложение, которое должно выполняться с PowerShell). В этом случае нельзя использовать чистые базовые сборки. Вместо этого проект будет зависеть от конкретной реализации PowerShell. Поскольку необходимо использовать конкретную реализацию PowerShell, для размещения требуется выбрать определенную версию PowerShell. Одно ведущее приложение не может быть предназначено для нескольких целевых версий PowerShell.

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a>Публикация проектов для PowerShell в виде ссылки

> [!NOTE]
> В этой статье под **публикацией** мы подразумеваем выполнение `dotnet publish`, в результате которого библиотека .NET помещается в каталог со всеми зависимостями, готовая к развертыванию в определенной среде выполнения.

Чтобы предотвратить публикацию зависимостей проекта, которые используются только как базовые целевые объекты при компиляции, рекомендуется задать [атрибут PrivateAssets][].

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

Если вы забудете сделать это и используете базовую сборку в качестве целевого объекта, могут возникнуть проблемы, связанные с использованием реализации базовой сборки по умолчанию вместо фактической реализации. Может возникнуть исключение `NullReferenceException`, так как базовые сборки часто используют макет реализации API, просто возвращая `null`.

## <a name="key-kinds-of-powershell-targeting-net-projects"></a>Основные типы проектов .NET для PowerShell

Хотя PowerShell может быть встроен в любую библиотеку или приложение .NET, некоторые сценарии использования API PowerShell более популярны.

- **Реализация двоичного модуля PowerShell**

  Двоичные модули PowerShell — это библиотеки .NET, загружаемые с помощью PowerShell, которые должны реализовывать API PowerShell как типы [PSCmdlet][] или [CmdletProvider][], чтобы предоставить доступ к командлетам или поставщикам соответственно. Так как они загружены, модули стараются выполнить компиляцию по ссылкам на PowerShell без публикации его в сборке. Часто модули предназначены для нескольких версий и платформ PowerShell, в идеале требуя минимум дискового пространства, сложных действий или повторной реализации. Дополнительные сведения о модулях см. в разделе [about_Modules][].

- **Реализация узла PowerShell**

  Узел PowerShell предоставляет уровень взаимодействия для среды выполнения PowerShell. Это определенная форма _размещения_, в которой [PSHost][] реализован в качестве нового пользовательского интерфейса для PowerShell. Например, PowerShell ConsoleHost предоставляет пользовательский интерфейс терминала для исполняемых файлов PowerShell, а узел служб редактора PowerShell и узел ISE предоставляют встроенный в редактор частично графический пользовательский интерфейс на основе PowerShell. Хотя вы можете загрузить узел в существующий процесс PowerShell, обычно он представлен как автономная реализация PowerShell, распространяющая подсистему PowerShell.

- **Вызов PowerShell из другого приложения .NET**

  Как и в любом другом приложении, PowerShell можно вызывать как подпроцесс для выполнения рабочих нагрузок. В приложениях .NET можно также вызвать PowerShell внутри процесса для возврата полных объектов .NET для использования в вызывающем приложении. Это более общая форма _размещения_, в которой приложение содержит собственную реализацию PowerShell для внутреннего использования. Например, это может быть служба или управляющая программа, выполняющая PowerShell для управления состоянием компьютера или веб-приложением, которое запускает PowerShell по запросу, чтобы управлять облачными развертываниями или выполнять другие задачи.

- **Модульное тестирование модулей PowerShell из .NET**

  Хотя модули и другие библиотеки, предназначенные для предоставления функциональных возможностей PowerShell, должны тестироваться главным образом в PowerShell (мы рекомендуем [Pester][]), иногда необходимо выполнить модульные тесты API, написанные для модуля PowerShell, в .NET. В этой ситуации код модуля пытается выбрать несколько версий PowerShell, а тестирование должно выполняться в конкретных реализациях.

## <a name="powershell-nuget-packages-at-a-glance"></a>Краткий обзор пакетов NuGet для PowerShell

В этой статье рассматриваются следующие пакеты NuGet, которые предоставляют API-интерфейсы PowerShell.

- [PowerShellStandard.Library][] — базовая сборка, позволяющая создавать одну сборку, которую можно загрузить несколькими средами выполнения PowerShell.
- [Microsoft.PowerShell.SDK][] — способ назначения и повторного размещения всего пакета SDK для PowerShell
- Пакет [System.Management.Automation][] — основная среда выполнения PowerShell и реализация ядра, которые могут быть полезны в минимальных размещенных реализациях и сценариях нацеливания на конкретные версии.
- **Базовые сборки Windows PowerShell** — это способ назначения и эффективного повторного размещения Windows PowerShell (PowerShell версии 5.1 и более ранних).

> [!NOTE]
> Пакет [PowerShell NuGet][] не входит в библиотеку .NET, но предоставляет реализацию глобального средства PowerShell dotnet. Он не должен использоваться проектами, так как предоставляет только исполняемый файл.

## <a name="powershellstandardlibrary"></a>PowerShellStandard.Library

Стандартная библиотека PowerShell — это базовая сборка, которая фиксирует пересечение API PowerShell версий 7, 6 и 5.1. Она предоставляет поверхность API, проверенную во время компиляции, для компиляции кода .NET, позволяя нацеливать проекты .NET на версии 7, 6 и 5.1 без риска вызвать отсутствующий API.

PowerShell Standard используется для написания модулей PowerShell или другого кода, предназначенного для запуска только после его загрузки в процесс PowerShell. Так как это базовая сборка, PowerShell Standard не содержит саму реализацию и не предоставляет функциональные возможности для автономных приложений.

### <a name="using-powershell-standard-with-different-net-runtimes"></a>Использование PowerShell Standard с разными средами выполнения .NET

PowerShell Standard предназначен для целевой среды выполнения [.NET Standard 2.0][], которая предоставляет общую контактную зону, совместно используемую .NET Framework и .NET Core. Это позволяет выбрать одну среду выполнения в качестве целевой, чтобы создать одну сборку, которая будет работать с несколькими версиями PowerShell. Но существуют некоторые ограничения.

- Для загрузки модуля или библиотеки в PowerShell необходима версия не ниже .NET 4.6.1; .NET 4.6 и .NET 4.5.2 не поддерживают .NET Standard. Обратите внимание, что новая версия Windows PowerShell не означает более новую версию .NET Framework. Windows PowerShell 5.1 может работать на платформе .NET 4.5.2.
- Чтобы работать с PowerShell на .NET Framework 4.7.1 или более ранней версии, требуется реализация .NET 4.6.1 [NETStandard.Library][], которая предоставляет netstandard.dll и другие сборки оболочек совместимости в более ранних версиях .NET Framework.

PowerShell 6+ предоставляет собственные сборки оболочек совместимости для перенаправления типов из .NET Framework 4.6.1 (и более поздних версий) в .NET Core. Это означает, что, пока модуль использует только API, существующие в .NET Core, PowerShell 6+ может загрузить и запустить его, если он создан для .NET Framework 4.6.1 (целевой объект среды выполнения `net461`).

То есть для двоичных модулей, использующих PowerShell Standard для нацеливания на несколько версий PowerShell с одной опубликованной библиотекой DLL, существует два варианта.

1. Публикация сборки, созданной для целевой среды выполнения `net461`. Сюда входит:
   - публикация проекта для среды выполнения `net461`;
   - компиляция в среде выполнения `netstandard2.0` (без использования выходных данных сборки), чтобы все используемые API также существовали в .NET Core.

1. Публикация сборки, созданной для целевой среды выполнения `netstandard2.0`. Для этого требуется:
   - публикация проекта для среды выполнения `netstandard2.0`;
   - получение зависимостей `net461` NETStandard.Library и копирование их в расположение публикации сборки, чтобы исправлять сборку с учетом перенаправления типов в .NET Framework.

Для создания модулей или библиотек PowerShell, предназначенных для более ранних версий .NET Framework, лучше выбрать несколько сред выполнения .NET. При этом будет опубликована сборка для каждой целевой среды выполнения и во время загрузки модуля нужно будет загрузить подходящую сборку (например, с небольшим PSM1-файлом в качестве корневого модуля).

### <a name="testing-powershell-standard-projects-in-net"></a>Тестирование проектов PowerShell Standard в .NET

При тестировании модуля в средствах выполнения тестов .NET, таких как xUnit, помните, что проверки времени компиляции имеют ограничения. Модуль необходимо протестировать на соответствующих платформах PowerShell.

Для тестирования API, созданных на основе PowerShell Standard в .NET, следует добавить `Microsoft.Powershell.SDK` как зависимость тестирования с .NET Core (с набором версий, соответствующим нужной версии PowerShell), и соответствующие базовые сборки Windows PowerShell с .NET Framework.

Дополнительные сведения о PowerShell Standard и его использовании для написания двоичного модуля, работающего в нескольких версиях PowerShell, см. в [этой записи блога][]. См. также раздел [репозиторий PowerShell Standard][] на сайте GitHub.

## <a name="microsoftpowershellsdk"></a>Microsoft.PowerShell.SDK

`Microsoft.PowerShell.SDK` — это метапакет, который объединяет все компоненты пакета SDK PowerShell в один пакет NuGet. Автономное приложение .NET может использовать Microsoft.PowerShell.SDK для запуска произвольных функций PowerShell, не завися от внешних установок или библиотек PowerShell.

> [!NOTE]
> Пакет SDK PowerShell ссылается на все пакеты компонентов, которые составляют PowerShell и которые можно использовать для разработки в .NET с помощью PowerShell.

Заданная версия `Microsoft.Powershell.SDK` содержит конкретную реализацию той же версии приложения PowerShell. Версия 7.0 содержит реализацию PowerShell 7.0, и выполнение команд или скриптов в этой версии будет во многом аналогично их выполнению в PowerShell 7.0.

Выполнение команд PowerShell из пакета SDK происходит почти так же, как и в `pwsh`, с небольшими отличиями. Например, [Start-Job][] в данный момент зависит от исполняемого файла `pwsh` и не будет работать с `Microsoft.Powershell.SDK` по умолчанию.

Нацеливание на `Microsoft.Powershell.SDK` из приложения .NET позволяет обеспечить интеграцию со всеми сборками реализации PowerShell, такими как `System.Management.Automation`, `Microsoft.PowerShell.Management` и другие сборки модулей.

При публикации приложения, нацеленного на `Microsoft.Powershell.SDK`, будут включены все эти сборки, а также все зависимости, необходимые для PowerShell. Также будут включены другие ресурсы, требуемые для сборки PowerShell, такие как манифесты модулей для модулей `Microsoft.PowerShell.*` и каталог `ref`, необходимый для [Add-Type][].

Учитывая полноту пакета `Microsoft.Powershell.SDK`, он лучше всего подходит для следующих целей.

- Реализация узлов PowerShell.
- Тестирование xUnit для библиотек, предназначенных для базовых сборок PowerShell.
- Вызов PowerShell в процессе из приложения .NET.

`Microsoft.PowerShell.SDK` также может использоваться как базовый целевой объект, если проект .NET предназначен для использования в качестве модуля или иным образом загружается PowerShell, но зависит от API, имеющихся только в определенной версии PowerShell. Обратите внимание, что сборку, опубликованную для конкретной версии `Microsoft.PowerShell.SDK`, можно безопасно загружать и использовать только в этой версии PowerShell. Чтобы использовать несколько версий PowerShell с конкретными API, требуется несколько сборок, каждая из которых нацелена на собственную версию `Microsoft.Powershell.SDK`.

> [!NOTE]
> Пакет SDK PowerShell доступен только для PowerShell версии 6 и выше. Чтобы обеспечить эквивалентную функциональность в Windows PowerShell, используйте базовые сборки Windows PowerShell, описанные ниже.

## <a name="systemmanagementautomation"></a>System.Management.Automation

Пакет `System.Management.Automation` является основой пакета SDK для PowerShell. Он существует в NuGet в основном в качестве ресурса для `Microsoft.Powershell.SDK`. Однако его также можно использовать непосредственно в качестве пакета для небольших сценариев размещения и модулей для конкретных версий.

В частности, пакет `System.Management.Automation` может быть предпочтительным источником функций PowerShell в следующих случаях.

- Вы хотите использовать только функции языка PowerShell (в пространстве имен `System.Management.Automation.Language`), такие как средства синтаксического анализа PowerShell, AST и API посетителя AST (например, для статического анализа PowerShell).
- Вам нужно выполнить только определенные команды из модуля `Microsoft.PowerShell.Core` и вы можете выполнять их в состоянии сеанса, созданного с помощью фабричного метода [CreateDefault2][].

Кроме того, `System.Management.Automation` полезно использовать в качестве базовой сборки в следующих случаях.

- Вы хотите ориентироваться на API, которые находятся только в определенной версии PowerShell.
- Вы не будете зависеть от типов вне сборки `System.Management.Automation` (например, типов, экспортированных командлетами в модули `Microsoft.PowerShell.*`).

## <a name="windows-powershell-reference-assemblies"></a>Базовые сборки Windows PowerShell

Для PowerShell версии 5.1 и более ранних версий (Windows PowerShell) пакет SDK для реализации PowerShell отсутствует, так как реализация Windows PowerShell является частью Windows.

Вместо этого базовые сборки Windows PowerShell предоставляют ссылки на базовые целевые объекты и способ повторного размещения Windows PowerShell, выполняя те же задачи, что и пакет SDK для PowerShell в версиях 6 и более поздних.

Базовые сборки Windows PowerShell не различаются по версиям, но имеют разные пакеты для каждой версии Windows PowerShell.

- [PowerShell 5.1](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [PowerShell 4](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [PowerShell 3](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

Сведения о том, как использовать базовые сборки Windows PowerShell, можно найти в разделе о [пакете SDK Windows PowerShell][].

## <a name="real-world-examples-using-these-nuget-packages"></a>Реальные примеры использования пакетов NuGet

Различные проекты инструментов PowerShell предназначены для различных пакетов NuGet PowerShell в зависимости от их потребностей. Ниже приведены некоторые основные примеры.

### <a name="psreadline"></a>PSReadLine

[PSReadLine][] — модуль PowerShell, который предоставляет большую часть возможностей консоли PowerShell, ориентирован на PowerShell Standard в качестве зависимости, а не определенной версии PowerShell, а в его файле [CSPROJ][] указана среда выполнения .NET `net461`.

PowerShell 6+ предоставляет собственные сборки оболочек совместимости, благодаря которым библиотека DLL, предназначенная для среды выполнения `net461`, работает без настройки при загрузке (путем перенаправления привязки к .`mscorlib.dll` NET Framework в соответствующую сборку .NET Core).

Это значительно упрощает макет и доставку модулей PSReadLine, так как PowerShell Standard гарантирует, что только используемые API будут присутствовать как в PowerShell 5.1, так и в PowerShell 6 и более поздних версий, а модуль будет поставлять только одну сборку.

Но при выборе .NET 4.6.1 в качестве целевой платформы Windows PowerShell на .NET 4.5.2 и .NET 4.6 не поддерживается.

### <a name="powershell-editor-services"></a>Службы редактора PowerShell

[Службы редактора PowerShell][] (PSES) — это серверная часть для [расширения PowerShell][] для [Visual Studio Code][] и, по сути, представляет собой модуль PowerShell, который загружается исполняемым файлом PowerShell, а затем берет контроль над процессом для повторного размещения PowerShell внутри себя, при этом предоставляя возможности протокола языковой службы и адаптера отладки.

PSES предоставляет конкретные целевые объекты реализации для `netcoreapp2.1`, чтобы выбрать PowerShell 6+ в качестве целевой платформы (так как среда выполнения `netcoreapp3.1` PowerShell 7 имеет обратную совместимость), и `net461` для Windows PowerShell 5.1, но содержит большую часть логики во второй сборке, ориентированной на `netstandard2.0` и PowerShell Standard. Это позволяет извлекать зависимости, необходимые для платформ .NET Core и .NET Framework, при этом упростить большую часть базы кода, скрывая ее за единообразной абстракцией.

Поскольку служба PSES создана на основе PowerShell Standard, для тестирования требуется реализация среды выполнения PowerShell. Для этого тесты [xUnit PSES][] используют `Microsoft.PowerShell.SDK` и `Microsoft.PowerShell.5.ReferenceAssemblies`, чтобы предоставить реализацию PowerShell в тестовой среде.

Как и в случае с PSReadLine, PSES не поддерживает .NET 4.6 и более ранних версий, но [выполняет проверку][] во время выполнения перед вызовом API, который может вызвать аварийное завершение в средах выполнения .NET Framework более ранней версии.

### <a name="psscriptanalyzer"></a>PSScriptAnalyzer

[PSScriptAnalyzer][], анализатор кода для PowerShell, должен быть нацелен на синтаксические элементы, представленные только в определенных версиях PowerShell. Поскольку распознавание этих синтаксических элементов выполняется путем реализации [AstVisitor2][], невозможно использовать PowerShell Standard, а также реализовать методы посетителей AST для новых синтаксисов PowerShell.

Вместо этого PSScriptAnalyzer [ориентируется на каждую версию PowerShell][] в качестве конфигурации сборки и создает отдельную библиотеку DLL для каждой из них. Это увеличивает размер сборки и сложность, но дает следующие преимущества.

- Нацеливание на API для конкретной версии.
- Функции, зависящие от версии, реализуются практически без затрат в среде выполнения.
- Общая поддержка Windows PowerShell вплоть до .NET Framework 4.5.2.

## <a name="summary"></a>Сводка

В этой статье мы рассмотрели и обсудили пакеты NuGet, доступные при реализации проекта .NET, который использует PowerShell, а также области их применения.

Если вы перешли сразу к сводке, ознакомьтесь со следующими рекомендациями.

- **Модули** PowerShell должны компилироваться в PowerShell Standard, если им требуются только API, общие для разных версий PowerShell.
- **Узлы и приложения** PowerShell, для которых требуется внутреннее выполнение PowerShell, должны ориентироваться на пакет SDK PowerShell для PowerShell 6+ или соответствующие базовые сборки Windows PowerShell для Windows PowerShell.
- Модули PowerShell, которым требуются **API для конкретных версий**, должны ориентироваться на пакет SDK PowerShell или базовые сборки Windows PowerShell для требуемых версий PowerShell, используя их в качестве базовых сборок (то есть не публикуя зависимости PowerShell).

<!--link references -->

[.NET Standard 2.0]: /dotnet/standard/net-standard
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[Add-Type]: /powershell/module/microsoft.powershell.utility/add-type
[AstVisitor2]: /dotnet/api/system.management.automation.language.astvisitor2
[CmdletProvider]: /dotnet/api/system.management.automation.provider.cmdletprovider
[CreateDefault2]: /dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2
[csproj]: https://github.com/PowerShell/PSReadLine/blob/master/PSReadLine/PSReadLine.csproj
[Microsoft.PowerShell.SDK]: https://www.nuget.org/packages/Microsoft.PowerShell.SDK/
[NETStandard.Library]: https://www.nuget.org/packages/NETStandard.Library/
[NuGet]: https://www.nuget.org/
[выполняет проверку]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[Pester]: https://github.com/Pester/Pester
[Службы редактора PowerShell]: https://github.com/PowerShell/PowerShellEditorServices/
[Расширение PowerShell]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[NuGet PowerShell]: https://www.nuget.org/packages/PowerShell/
[репозиторий PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[PSES xUnit]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[атрибут PrivateAssets]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[базовые сборки]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[ориентируется на каждую версию PowerShell]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[эту запись блога]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[Пакет SDK для Windows PowerShell]: /powershell/scripting/developer/windows-powershell
