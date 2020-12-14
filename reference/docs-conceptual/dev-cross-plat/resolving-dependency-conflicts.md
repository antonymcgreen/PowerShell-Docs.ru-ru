---
title: Разрешение конфликтов зависимостей сборок для модулей PowerShell
description: При написании двоичного модуля PowerShell в C# можно использовать зависимости от других пакетов или библиотек для дополнительных функциональных возможностей.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 93bb39bdd440c7f97c27aa81e68f68331569b69e
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810408"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a>Разрешение конфликтов зависимостей сборок для модулей PowerShell

При написании двоичного модуля PowerShell в C# можно использовать зависимости от других пакетов или библиотек для дополнительных функциональных возможностей. Зависимости от других библиотек помогают повторно использовать код. PowerShell всегда загружает сборки в один и тот же контекст. В результате зависимости модуля могут конфликтовать с уже загруженными библиотеками DLL и вы не сможете использовать два несвязанных модуля в одном сеансе PowerShell.

Если у вас возникла эта проблема, отображается сообщение об ошибке следующего вида.

![Сообщение об ошибке конфликта при загрузке сборки](./media/resolving-dependency-conflicts/moduleconflict.png)

В этой статье рассматривается, как возникают конфликты зависимостей в PowerShell и как можно их устранить. Даже если вы не являетесь автором модуля, вы можете принять меры, чтобы решить проблему конфликта зависимостей в модулях, которые вы используете.

## <a name="why-do-dependency-conflicts-occur"></a>Почему возникают конфликты зависимостей?

В .NET конфликты зависимостей возникают, когда две версии одной сборки загружаются в один и тот же _контекст загрузки сборок_. Точное значение этого термина зависит от платформы .NET, и об этом мы поговорим [позже](#powershell-and-net). Этот конфликт часто возникает в программном обеспечении, где используются зависимости с версиями. Поскольку простых решений не существует и многие платформы разрешения зависимостей пытаются решить проблему разными способами, такая ситуация часто называется dependency hell, то есть "ад зависимостей".

Проблемы, связанные с конфликтами, осложняются тем фактом, что проект почти никогда намеренно или напрямую не зависит от двух версий одной и той же зависимости. Вместо этого проект имеет две зависимости или более, для каждой из которых требуется своя версия одной зависимости.

Предположим, что приложение .NET, `DuckBuilder`, включает в себя две зависимости для разных функций и выглядит следующим образом.

![Две зависимости от DuckBuilder требуют разных версий Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

Так как `Contoso.ZipTools` и `Fabrikam.FileHelpers` зависят от разных версий `Newtonsoft.Json`, может возникнуть конфликт зависимостей исходя из способа загрузки каждой зависимости.

### <a name="conflicting-with-powershells-dependencies"></a>Конфликт с зависимостями PowerShell

В PowerShell проблема с конфликтом зависимостей усугубляется, так как модули PowerShell и собственные зависимости PowerShell загружаются в один и тот же общий контекст. Это означает, что обработчик PowerShell и все загруженные модули PowerShell не должны иметь конфликтующих зависимостей. Классический пример — `Newtonsoft.Json`.

![Модуль FictionalTools зависит от более новой версии Newtonsoft.Json, чем PowerShell](./media/resolving-dependency-conflicts/engine-conflict.jpg)

В этом примере модуль `FictionalTools` зависит от версии `Newtonsoft.Json` `12.0.3`, которая является более новой версией `Newtonsoft.Json`, чем `11.0.2` в PowerShell.

> [!NOTE]
> Это просто пример; сейчас PowerShell 7 поставляется с `Newtonsoft.Json 12.0.3`.

Поскольку модуль зависит от более новой версии сборки, он не принимает версию, которая уже загружена в PowerShell. Но раз PowerShell уже загрузил версию сборки, модуль не может загрузить собственную версию с помощью стандартного механизма загрузки.

### <a name="conflicting-with-another-modules-dependencies"></a>Конфликт с зависимостями другого модуля

Еще один распространенный сценарий в PowerShell — загрузка двух модулей, которые зависят от разных версий одной сборки.

Часто это выглядит следующим образом.

![Для двух модулей PowerShell требуются разные версии зависимости Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

В этом случае для модуля `FictionalTools` требуется более новая версия `Microsoft.Extensions.Logging`, чем для модуля `FilesystemManager`.

Представьте, что эти модули загружают свои зависимости, помещая сборки зависимостей в тот же каталог, где находится сборка корневого модуля. Это позволяет платформе .NET неявно загружать их по имени. Если вы используете PowerShell 7 (на платформе .NET Core 3.1), можно загрузить и запустить `FictionalTools`, а затем загрузить и запустить `FilesystemManager` без проблем. Однако в новом сеансе, если мы загружаем и запускаем `FilesystemManager`, а затем загружаем `FictionalTools`, мы получаем `FileLoadException` из команды `FictionalTools`, так как для нее требуется более новая версия `Microsoft.Extensions.Logging`, чем загруженная.
`FictionalTools` не удается загрузить требуемую версию, так как сборка с таким именем уже загружена.

## <a name="powershell-and-net"></a>PowerShell и .NET

PowerShell выполняется на платформе .NET. .NET отвечает за разрешение и загрузку зависимостей сборок, поэтому мы должны понимать, как работает .NET, чтобы разбираться в конфликтах зависимостей.

Кроме того, мы должны принять тот факт, что разные версии PowerShell работают в различных реализациях .NET. Как правило, PowerShell 5.1 и более ранних версий работает на .NET Framework, а PowerShell 6 и более поздних версий — на .NET Core. Эти две реализации .NET загружают и обрабатывают сборки по-разному.
Это означает, что конфликты зависимостей по-разному разрешаются на разных платформах .NET.

### <a name="assembly-load-contexts"></a>Контексты загрузки сборок

В .NET _контекст загрузки сборок_ (ALC) — это пространство имен среды выполнения, в которое загружаются сборки. Имена сборок должны быть уникальными. Эта концепция позволяет уникально разрешать сборки по имени в каждом контексте загрузки сборок.

### <a name="assembly-reference-loading-in-net"></a>Загрузка ссылок на сборки в .NET

Семантика загрузки сборок зависит как от реализации .NET (.NET Core или .NET Framework), так и от .NET API, используемого для загрузки определенной сборки. Мы не будем останавливаться на этом, но в разделе [Дополнительные ресурсы](#further-reading) приводятся ссылки на статьи о том, как работает загрузка сборок .NET в каждой реализации .NET.

В этой статье мы будем упоминать следующие механизмы.

- Неявная загрузка сборки (`Assembly.Load(AssemblyName)`), когда .NET неявно пытается загрузить сборку по имени из ссылки на статическую сборку в коде .NET.
- `Assembly.LoadFrom()`, ориентированный на подключаемый модуль API загрузки, который добавляет обработчики для разрешения зависимостей загруженной библиотеки DLL. Этот метод может не разрешать зависимости нужным образом.
- `Assembly.LoadFile()`, базовый API загрузки, предназначенный для загрузки только запрошенной сборки и не обрабатывающий зависимости.

### <a name="differences-in-net-framework-vs-net-core"></a>Различия между .NET Framework и .NET Core

Способ работы этих API немного различается в .NET Core и .NET Framework, поэтому изучите материалы по [ссылкам](#further-reading). Важно отметить, что контексты загрузки сборок и другие механизмы разрешения сборок различаются в .NET Framework и .NET Core.

В частности, .NET Framework имеет следующие возможности.

- Глобальный кэш сборок для разрешения сборок на уровне компьютера.
- Домены приложений, которые работают как внутрипроцессные песочницы для изоляции сборок, также представляют уровень сериализации, который следует учитывать.
- Ограниченная модель контекста загрузки сборок, подробно описанная [здесь](/dotnet/framework/deployment/best-practices-for-assembly-loading), имеет фиксированный набор контекстов загрузки сборок, каждый из которых имеет собственное поведение:
  - контекст загрузки по умолчанию, где сборки загружаются по умолчанию;
  - контекст, из которого выполняется загрузка, для загрузки сборок вручную во время выполнения;
  - контекст только для отражения, предназначенный для безопасной загрузки сборок для чтения их метаданных без запуска;
  - загадочное пространство, где находятся сборки, загруженные с помощью `Assembly.LoadFile(string path)` и `Assembly.Load(byte[] asmBytes)`.

В .NET Core (и .NET 5+) эти сложности заменены на упрощенную модель.

- Глобальный кэш сборок отсутствует. Приложения содержат все собственные зависимости. Это позволяет исключить внешний фактор для разрешения зависимостей в приложениях, благодаря чему разрешение зависимостей проще воспроизвести.
  PowerShell как узел подключаемого модуля немного усложняет этот процесс для модулей. Его зависимости в `$PSHOME` являются общими для всех модулей.
- Только один домен приложения без возможности создавать новые. Понятие предметной области приложения поддерживается в .NET Core исключительно для глобального состояния процесса .NET.
- Новая расширяемая модель контекста загрузки сборок. Для разрешения сборок можно использовать пространство имен, поместив его в новый контекст загрузки сборок. Процессы .NET Core начинаются с одного контекста загрузки сборок по умолчанию, в который загружаются все сборки (за исключением тех, которые были загружены с `Assembly.LoadFile(string)` и `Assembly.Load(byte[])`). Но процесс может создавать и определять собственные пользовательские контексты загрузки сборок с собственной логикой загрузки. При загрузке сборки первый контекст загрузки сборки, в который она загружается, отвечает за разрешение зависимостей. Это создает возможности для реализации мощных механизмов загрузки подключаемого модуля .NET.

В обеих реализациях сборки загружаются неактивно. То есть они загружаются, когда метод, запрашивающий их тип, выполняется в первый раз.

Например, ниже приведены две версии одного и того же кода, которые загружают зависимость в разное время.

Первый всегда загружает свою зависимость при вызове `Program.GetRange()`, так как ссылка на зависимость лексически представлена в методе:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

Вторая загружает зависимость только в том случае, если параметр `limit` имеет значение 20 или более, из-за внутреннего косвенного обращения через метод:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

Это хороший подход, поскольку он сводит к минимуму операции ввода-вывода в памяти и файловой системе и более эффективно использует ресурсы. Но есть и побочный эффект — мы не узнаем о сбое загрузки сборки, пока не достигнем пути к коду, пытающегося загрузить сборку.

Кроме того, при таком подходе возникают временные условия для конфликтов при загрузке сборки. Если две части одной и той же программы пытаются загрузить разные версии одной и той же сборки, то загружаемая версия зависит от того, какой путь к коду выполняется первым.

Для PowerShell это означает, что следующие факторы могут повлиять на конфликт загрузки сборки.

- Какой модуль загружен первым?
- Выполнялся ли путь к коду, использующий библиотеку зависимостей?
- Загружает ли PowerShell конфликтующую зависимость при запуске или только по определенным путям к коду?

## <a name="quick-fixes-and-their-limitations"></a>Быстрые исправления и их ограничения

В некоторых случаях можно внести небольшие изменения в модуль и исправить проблему с минимальными усилиями. Но эти решения обычно имеют свои особенности. Они могут применяться к конкретному модулю, но не являются универсальными.

### <a name="change-your-dependency-version"></a>Изменение версии зависимости

Самый простой способ избежать конфликтов зависимостей — согласовать зависимость. Это можно сделать в следующих случаях.

- У вас возник конфликт с прямой зависимостью модуля, и вы управляете версией.
- Конфликт связан с косвенной зависимостью, но вы можете настроить прямые зависимости для использования работоспособной версии косвенной зависимости.
- Вы знаете конфликтующую версию и можете быть уверены, что она не изменится.

Пакет `Newtonsoft.Json` — хороший пример последнего сценария. Это зависимость в PowerShell 6 и более поздних версий, которая не используется в Windows PowerShell. Простой способ разрешения конфликтов версий — использовать минимальную версию `Newtonsoft.Json` в нужных версиях PowerShell.

Например, PowerShell 6.2.6 и PowerShell 7.0.2 в настоящее время используют `Newtonsoft.Json` версии 12.0.3. Таким образом, чтобы создать модуль, предназначенный для Windows PowerShell, PowerShell 6 и PowerShell 7, нужно выбрать `Newtonsoft.Json 12.0.3` в качестве зависимости и включить его в созданный модуль. При загрузке модуля в PowerShell 6 или 7 собственная сборка `Newtonsoft.Json` PowerShell уже загружена. Кроме того, это как минимум версия, необходимая для вашего модуля, поэтому разрешение будет выполняться. В Windows PowerShell эта сборка еще отсутствует в PowerShell. Вместо этого она загружается из папки модуля.

Как правило, при выборе конкретного пакета PowerShell, например `Microsoft.PowerShell.Sdk` или `System.Management.Automation`, NuGet должен иметь возможность разрешить нужные версии зависимостей. Настроить нацеливание одновременно на Windows PowerShell и PowerShell 6+ сложнее, поскольку необходимо выбрать между нацеливанием на несколько платформ и `PowerShellStandard.Library`.

Использование общей версии не работает в следующих условиях.

- Конфликт связан с косвенной зависимостью, и ни одну из зависимостей нельзя настроить для использования общей версии.
- Другая версия зависимости часто меняется, поэтому выбор общей версии поможет лишь на время.

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a>Добавление обработчика событий AssemblyResolve для создания динамического перенаправления привязки

Иногда изменить свою версию зависимости невозможно или слишком сложно. Другой вариант — настроить перенаправление динамической привязки, зарегистрировав обработчик событий для события `AssemblyResolve`.

Как и в случае с перенаправлением статической привязки, нужно заставить всех потребителей зависимости использовать одну и ту же фактическую сборку. Вы перехватываете вызовы для загрузки зависимости и всегда перенаправляете их в нужную версию.

Это выглядит примерно так.

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

Конечно, вы могли бы зарегистрировать блок сценария в PowerShell, чтобы обрабатывать событие `AssemblyResolve`, но:

- Событие `AssemblyResolve` может быть запущено в любом потоке, и PowerShell тут бессилен.
- Даже если события обрабатываются в правильном потоке, область действия PowerShell требует внимательного написания блока сценариев обработчика событий, чтобы не зависеть от переменных, определенных за его пределами.

В некоторых ситуациях перенаправление на общую версию не будет работать.

- Если зависимость имеет критические изменения между версиями или если зависимый код использует функции, недоступные в версии, к которой выполняется перенаправление.
- Если модуль не загружен до конфликтующей зависимости. Если вы регистрируете обработчик событий `AssemblyResolve` после загрузки зависимости, он никогда не будет срабатывать. Если вы пытаетесь предотвратить конфликты зависимостей с другим модулем, это может быть проблематично в случае, когда другой модуль загружен первым.

### <a name="use-the-dependency-out-of-process"></a>Использование зависимости вне процесса

Это решение подходит скорее для пользователей, чем для авторов модулей. Это решение используется при взаимодействии с модулем, который не работает из-за существующего конфликта зависимостей.

Конфликты зависимостей возникают, когда две версии одной сборки загружаются в один и тот же процесс .NET. Простое решение — загрузить их в разные процессы, если вы по-прежнему сможете использовать эти функции одновременно.

В PowerShell это можно сделать несколькими способами.

- Вызов PowerShell в качестве подпроцесса

  Простой способ выполнить команду PowerShell вне текущего процесса — запустить новый процесс PowerShell непосредственно с помощью вызова команды:

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  Основное ограничение заключается в том, что реструктуризация результата может быть сложнее или более подвержена ошибкам, чем другие варианты.

- Система заданий PowerShell

  Система заданий PowerShell также выполняет команды вне процесса, отправляя команды новому процессу PowerShell и возвращая результаты.

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  В этом случае необходимо только убедиться, что все переменные и состояние передаются правильно.

  Система заданий также может быть несколько громоздкой при выполнении небольших команд.

- Удаленное взаимодействие PowerShell

  Если удаленное взаимодействие с PowerShell доступно, это может оказаться удобным вариантом выполнения команд вне процесса. При удаленном взаимодействии можно создать новый сеанс **PSSession** в новом процессе, вызвать его команды через удаленное взаимодействие с PowerShell, а затем использовать результаты локально с другими модулями, содержащими конфликтующие зависимости.

  Пример может выглядеть следующим образом.

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- Неявное удаленное взаимодействие с Windows PowerShell

  Еще один вариант в PowerShell 7 — использовать флаг `-UseWindowsPowerShell` в `Import-Module`. При этом модуль будет импортирован через локальный сеанс удаленного взаимодействия в Windows PowerShell.

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  Имейте в виду, что модули могут не работать с Windows PowerShell или работать иначе.

#### <a name="when-out-of-process-invocation-should-not-be-used"></a>Когда не следует использовать вызов вне процесса

Авторам модуля сложно внедрить в модуль вызов команды вне процесса, и в некоторых случаях могут возникать проблемы. В частности, удаленное взаимодействие и задания могут быть недоступны во всех средах, где должен работать ваш модуль. Но вы по-прежнему можете применять общий принцип перемещения реализации за пределы процесса и перевод модуля PowerShell в разряд более тонких клиентов.

Иногда пользователи модуля не могут использовать вызов вне процесса.

- Если удаленное взаимодействие с PowerShell недоступно из-за отсутствия у вас привилегий или отключено.
- Если в качестве входных данных для метода или другой команды требуется определенный тип .NET в выходных данных.
  Команды, выполняемые через удаленное взаимодействие с PowerShell, создают десериализованные объекты, а не строго типизированные объекты .NET. Это означает, что вызовы методов и строго типизированные API не работают с выходными данными команд, импортированных через удаленное взаимодействие.

## <a name="more-robust-solutions"></a>Более надежные решения

У всех предыдущих решений существуют исключения и ограничения, при этом их относительно просто реализовать. Следующие решения являются более надежными, но для их правильной реализации требуются дополнительные усилия и, если они не до конца продуманы, могут возникать незаметные ошибки.

### <a name="loading-through-net-core-assembly-load-contexts"></a>Загрузка с помощью контекстов загрузки сборок .NET Core

[Контексты загрузки сборок](/dotnet/api/system.runtime.loader.assemblyloadcontext) в качестве реализуемого API были представлены в .NET Core 1.0 специально для того, чтобы устранить необходимость загрузки нескольких версий одной сборки в одну и ту же среду выполнения.

В .NET Core и .NET 5 они являются самым надежным решением проблемы загрузки конфликтующих версий сборки. Однако пользовательские контексты загрузки сборок недоступны в .NET Framework. Это означает, что решение работает только в PowerShell 6 и более поздних версиях.

В настоящее время лучший пример использования контекстов загрузки сборок для изоляции зависимостей в PowerShell представлен в службах редактора PowerShell, языковом сервере для расширения PowerShell для Visual Studio Code. [Контекст загрузки сборок используется](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs), чтобы предотвратить конфликт собственных зависимостей служб редактора PowerShell с зависимостями в модулях PowerShell.

Реализовать изоляцию зависимостей модулей с помощью контекста загрузки сборок довольно сложно, но мы рассмотрим простейший пример. Представьте, что у нас есть простой модуль, предназначенный только для работы с PowerShell 7.
Исходный код организован следующим образом.

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

Реализация командлета выглядит следующим образом.

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

Манифест (в очень упрощенном виде) выглядит следующим образом.

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

А `csproj` выглядит так.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

При сборке этого модуля создаются выходные данные на основе следующего макета.

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

В этом примере наша проблема находится в сборке `Shared.Dependency.dll`, которая является нашей воображаемой конфликтующей зависимостью. Это зависимость, которую необходимо разместить за контекстом загрузки сборок, чтобы мы могли использовать версию для конкретного модуля.

Необходимо перестроить модуль таким образом, чтобы:

- Зависимости модуля загружаются только в пользовательский контекст загрузки сборок, а не в контекст PowerShell, чтобы конфликтов не возникало. Кроме того, по мере добавления зависимостей в проект мы не хотим постоянно добавлять код для поддержания работоспособности загрузки. Вместо этого мы хотим использовать многоразовую универсальную логику разрешения зависимостей.
- Загрузка модуля в PowerShell по-прежнему работает нормально. Командлеты и другие типы, необходимые системе модуля PowerShell, определяются в собственном контексте загрузки сборок в PowerShell.

Чтобы удовлетворить эти два требования, необходимо разделить модуль на две сборки.

- Сборка командлетов, `AlcModule.Cmdlets.dll`, содержащая определения всех типов, необходимых системе модуля PowerShell для правильной загрузки модуля. А именно: любые реализации базового класса `Cmdlet` и класса, реализующего `IModuleAssemblyInitializer`, который настраивает обработчик событий для `AssemblyLoadContext.Default.Resolving` для правильной загрузки `AlcModule.Engine.dll` через пользовательский контекст загрузки сборок. Поскольку в PowerShell 7 намеренно скрываются типы, определенные в сборках, загруженных в других контекстах загрузки сборок, все типы, которые должны быть общедоступными для PowerShell, также следует определить здесь. Наконец, в этой сборке необходимо указать определение пользовательского контекста загрузки сборок. Кроме того, в этой сборке должно быть как можно меньше кода.
- Сборка обработчика `AlcModule.Engine.dll`, которая обрабатывает фактическую реализацию модуля.
  Ее типы доступны в контексте загрузки сборок PowerShell, но изначально мы выполняем загрузку с помощью нашего пользовательского контекста загрузки сборок. Зависимости загружаются только в пользовательский контекст загрузки сборок. По сути, это что-то вроде _моста_ между двумя контекстами загрузки сборок.

Если продолжить сравнение с мостом, можно нарисовать следующую схему.

![Схема, представляющая AlcModule.Engine.dll как мост между двумя контекстами загрузки сборок](./media/resolving-dependency-conflicts/alc-diagram.jpg)

Чтобы убедиться, что логика проверки зависимостей в контексте загрузки сборок по умолчанию не разрешает загрузку зависимостей в пользовательский контекст загрузки сборок, необходимо разделить эти две части модуля на разные каталоги. Новый макет модуля имеет следующую структуру.

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

Чтобы увидеть, как изменяется реализация, мы начнем с реализации `AlcModule.Engine.dll`.

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

Это простой контейнер для зависимости, `Shared.Dependency.dll`, но его следует рассматривать как API .NET для функций, для которых командлеты в другой сборке служат оболочкой в PowerShell.

Командлет в `AlcModule.Cmdlets.dll` выглядит следующим образом.

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

На этом этапе, если нужно загрузить **AlcModule** и запустить `Test-AlcModule`, мы получаем `FileNotFoundException`, когда контекст загрузки сборок по умолчанию пытается загрузить `Alc.Engine.dll` для выполнения `EndProcessing()`. Это хорошо, так как это означает, что по умолчанию контекст загрузки сборок не может найти зависимости, которые мы хотим скрыть.

Теперь необходимо добавить код в `AlcModule.Cmdlets.dll`, чтобы он "знал", как разрешать `AlcModule.Engine.dll`. Сначала необходимо определить пользовательский контекст загрузки сборок, который будет разрешать сборки из каталога модуля `Dependencies`.

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _dependencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                _dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

Затем необходимо подключить пользовательский контекст загрузки сборок к событию `Resolving` по умолчанию, которое является версией события `AssemblyResolve` контекста загрузки сборок для доменов приложений. Это событие срабатывает для поиска `AlcModule.Engine.dll` при вызове `EndProcessing()`.

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

В новой реализации рассмотрим последовательность вызовов при загрузке модуля и запуске `Test-AlcModule`.

![Схема последовательности вызовов, использующих пользовательский контекст загрузки сборок для загрузки зависимостей](./media/resolving-dependency-conflicts/alc-sequence.png)

На что нужно обратить внимание.

- `IModuleAssemblyInitializer` выполняется первым, когда модуль загружает и настраивает событие `Resolving`.
- Мы не загружаем зависимости, пока не запустится `Test-AlcModule` и не будет вызван метод `EndProcessing()`.
- При вызове `EndProcessing()` контекст загрузки сборок по умолчанию не находит `AlcModule.Engine.dll` и запускает событие `Resolving`.
- Наш обработчик событий привязывает пользовательский контекст загрузки сборок к контексту загрузки сборок по умолчанию и загружает только `AlcModule.Engine.dll`.
- При вызове `AlcEngine.Use()` в `AlcModule.Engine.dll` пользовательский контекст загрузки сборок снова запускается для разрешения `Shared.Dependency.dll`. В частности, он всегда загружает _нашу_ библиотеку `Shared.Dependency.dll`, поскольку она никогда не конфликтует с содержимым контекста загрузки сборок по умолчанию и просматривает только наш каталог `Dependencies`.

При сборке реализации новый макет исходного кода выглядит следующим образом.

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

AlcModule.Cmdlets.csproj:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

AlcModule.Engine.csproj:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

Итак, наши действия при сборке модуля будут следующими.

- Выполнить сборку `AlcModule.Engine`.
- Выполнить сборку `AlcModule.Cmdlets`.
- Скопировать все из `AlcModule.Engine` в каталог `Dependencies` и запомнить, что мы скопировали.
- Скопировать все из `AlcModule.Cmdlets`, чего не было в `AlcModule.Engine`, в каталог базового модуля.

Так как структура модуля очень важна для разделения зависимостей, используйте следующий сценарий сборки из корневого каталога источника.

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

Наконец, у нас есть общий способ использовать контекст загрузки сборок для изоляции зависимостей модуля, который не теряет надежности по мере добавления дополнительных зависимостей.

Более подробный пример вы найдете в этом [репозитории GitHub](https://github.com/rjmholt/ModuleDependencyIsolationExample). В этом примере показано, как перенести модуль для использования контекста загрузки сборок, сохранив работоспособность этого модуля в .NET Framework. Здесь также показано, как использовать .NET Standard и PowerShell Standard для упрощения основной реализации.

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a>Обработчик разрешения сборки для параллельной загрузки с помощью `Assembly.LoadFile()`

Еще один, возможно, более простой способ достижения параллельной загрузки сборок заключается в подключении события `AssemblyResolve` к `Assembly.LoadFile()`. Преимущество использования `Assembly.LoadFile()` заключается в том, что это решение проще всего реализовать и оно подходит как для .NET Core, так и для .NET Framework.

Чтобы продемонстрировать это, давайте рассмотрим краткий пример реализации, объединяющей идеи из нашего примера перенаправления динамической привязки и примера контекста загрузки сборок.

Мы вызовем модуль **LoadFileModule** с простой командой `Test-LoadFile [-Path] <path>`. Этот модуль принимает зависимость от сборки `CsvHelper` (версия 15.0.5).

Как и в случае с модулем контекста загрузки сборок, сначала необходимо разделить модуль на две части.

Первая часть выполняет фактическую реализацию `LoadFileModule.Engine`.

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

Вторая часть — это то, что PowerShell загружает напрямую, `LoadFileModule.Cmdlets`. Мы используем стратегию, похожую на модуль контекста загрузки сборок, где мы изолируем зависимости в отдельном каталоге. Но на этот раз мы загружаем все сборки с событием разрешения, а не просто библиотеку `LoadFileModule.Engine.dll`.

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

Наконец, макет модуля аналогичен модулю контекста загрузки сборок.

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

В этой структуре **LoadFileModule** теперь можно загружать вместе с другими модулями с зависимостью от **CsvHelper**.

Так как наш обработчик применяется ко **всем** событиям `AssemblyResolve` в домене приложения, необходимо принять некоторые решения по проектированию.

- Чтобы сузить интервал, в котором наше событие может помешать другой загрузке, мы начинаем обработку общей загрузки зависимостей только после загрузки `LoadFileModule.Engine.dll`.
- Мы отправим `LoadFileModule.Engine.dll` в каталог зависимостей, чтобы он загружался вызовом `LoadFile()`, а не через PowerShell. Это означает, что собственные загрузки зависимостей всегда вызывают событие `AssemblyResolve`, даже если в PowerShell загружается другая библиотека `CsvHelper.dll` (например).
  Это дает нам возможность найти правильную зависимость.
- Так как мы должны разрешать только определенные зависимости для нашего модуля, мы вынуждены записать словарь имен и версий зависимостей в обработчике. В нашем случае можно было бы использовать свойство `ResolveEventArgs.RequestingAssembly`, чтобы определить, запрашивается ли `CsvHelper` в нашем модуле. Но это не работает для зависимостей зависимостей. Например, если `CsvHelper` вызывает событие `AssemblyResolve`. Есть и другие, более трудные способы выполнить эту задачу, например сравнить запрошенные сборки с метаданными сборок в каталоге `Dependencies`. Но в этом примере мы сделали эту проверку более явной, чтобы выделить проблемы и упростить пример.

Это ключевое различие между стратегией `LoadFile()` и использованием контекста загрузки сборок: событие `AssemblyResolve` должно обслуживать все нагрузки в домене приложения, поэтому нам гораздо сложнее изолировать наше разрешение зависимостей от других модулей. Поскольку в .NET Framework отсутствуют контексты загрузки сборок, стоит разобраться в этом варианте.

### <a name="custom-application-domains"></a>Пользовательские домены приложений

Последний и самый крайний вариант изоляции сборок — использовать пользовательские домены приложений.
Домены приложений (во множественном числе) доступны только в .NET Framework. Они используются для обеспечения внутрипроцессной изоляции между частями приложения .NET. Одно из их применений — изоляция загрузки сборок друг от друга в рамках одного процесса.

Однако домены приложений являются границами сериализации. На объекты в одном домене приложения нельзя ссылаться с помощью объектов в другом домене приложения. Кроме того, их нельзя использовать в другом домене. Для решения этой проблемы можно реализовать `MarshalByRefObject`. Но если вы не управляете типами, как это часто бывает с зависимостями, вы не сможете принудительно реализовать реализацию. Единственное решение — существенно изменить архитектуру. Граница сериализации также серьезно влияет на производительность.

Так как у доменов приложений есть такое серьезное ограничение, их сложно реализовать и они работают только в .NET Framework, мы не будем приводить примеры. Следует знать, что существует такая возможность, но лучше ее не использовать.

Если вы хотите попробовать пользовательский домен приложения, см. следующие ссылки.

- [Основная документация по доменам приложений](/dotnet/framework/app-domains/application-domains)
- [Примеры использования доменов приложений](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a>Решения для конфликтов зависимостей, которые не работают в PowerShell

Наконец, мы рассмотрим возможности, которые возникают при изучении конфликтов зависимостей .NET. Они могут показаться полезными, но обычно не работают в PowerShell.

Все эти решения представляют собой изменения конфигураций развертывания для среды, в которой вы управляете приложением и, возможно, всем компьютером. Эти решения ориентированы на такие сценарии, как веб-серверы и другие приложения, развернутые в серверных средах, где среда предназначена для размещения приложения и может быть настроена пользователем, выполняющим развертывание. Они также обычно ориентированы на .NET Framework, то есть не работают с PowerShell 6 или более поздней версии.

Если вы уверены, что ваш модуль используется только в средах Windows PowerShell 5.1, которые вы полностью контролируете, некоторые из этих вариантов могут оказаться полезными для вас. Но, как правило, **модули не должны изменять состояние глобального компьютера таким образом**. Это может нарушить конфигурации и привести к проблемам в `powershell.exe`, других модулях или других зависимых приложениях, из-за которых ваш модуль работает непредвиденным образом.

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a>Перенаправление статической привязки с помощью app.config для принудительного использования одинаковой версии зависимости

Приложения .NET Framework могут использовать преимущества файла `app.config`, чтобы декларативно настроить некоторые реакции приложения на события. Можно создать запись `app.config`, которая настраивает привязку сборки для перенаправления загрузки сборки в определенную версию.

В PowerShell у такого сценария есть две проблемы.

- .NET Core не поддерживает `app.config`, поэтому это решение применимо только к `powershell.exe`.
- `powershell.exe` — это общее приложение, которое находится в каталоге `System32`. Скорее всего, ваш модуль не сможет изменить его содержимое во многих системах. Даже если это возможно, изменение `app.config` может нарушить существующую конфигурацию или повлиять на загрузку других модулей.

### <a name="setting-codebase-with-appconfig"></a>Установка `codebase` с помощью app.config

По тем же причинам попытка настроить параметр `codebase` в `app.config` не будет работать в модулях PowerShell.

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a>Установка зависимостей в глобальный кэш сборок

Еще один способ разрешить конфликты версий зависимостей в .NET Framework — установить зависимости в глобальный кэш сборок, чтобы разные версии можно было загружать из него параллельно.

И снова для модулей PowerShell возникает несколько проблем.

- Глобальный кэш сборок применяется только к .NET Framework, поэтому его нельзя использовать в PowerShell 6 и более поздних версиях.
- Установка сборок в глобальный кэш сборок — это изменение состояния глобального компьютера, которое может привести к побочным эффектам в других приложениях или других модулях. Кроме того, это может усложнить работу, даже если ваш модуль имеет необходимые права доступа. Если сделать что-то неправильно, могут возникнуть серьезные проблемы на уровне компьютера в других приложениях .NET.

## <a name="further-reading"></a>Дополнительные сведения

Существует множество статей о конфликтах зависимостей версий сборок .NET. Рекомендуем начать изучение со следующих ресурсов.

- [.NET: сборки в .NET](/dotnet/standard/assembly/)
- [.NET Core: алгоритм загрузки управляемых сборок](/dotnet/core/dependency-loading/loading-managed)
- [.NET Core: основные сведения о System.Runtime.Loader.AssemblyLoadContext](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [.NET Core: обсуждение решений для параллельной загрузки сборок](https://github.com/dotnet/runtime/issues/13471)
- [.NET Framework: перенаправление версий сборки](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [.NET Framework: рекомендации для загрузки сборок](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [.NET Framework: обнаружение сборок в среде выполнения](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [.NET Framework: разрешение загрузки сборок](/dotnet/standard/assembly/resolve-loads)
- [StackOverflow: методы и причины перенаправления привязки сборок](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [PowerShell: обсуждение реализации AssemblyLoadContexts](https://github.com/PowerShell/PowerShell/issues/11571)
- [PowerShell: `Assembly.LoadFile()` не загружается в AssemblyLoadContext по умолчанию](https://github.com/PowerShell/PowerShell/issues/12052)
- [Рик Штраль (Rick Strahl): "Когда загружается зависимость сборки .NET?"](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [Джон Скит (Jon Skeet): "Общие сведения об управлении версиями в .NET"](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [Нейт Мак-Мастер (Nate McMaster): "Подробный обзор примитивов .NET Core"](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
