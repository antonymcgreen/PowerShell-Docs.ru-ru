---
title: Добавление псевдонимов, расширение подстановочных знаков и Справка по параметрам командлетов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 244c50c73972c2760e0029c7fa4f4b5764b066da
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774972"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a>Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета

В этом разделе описывается, как добавлять псевдонимы, распознавать подстановочные знаки и сообщения справки для параметров командлета "прекращать-proc" (описывается в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md)).

Этот командлет останавливает процесс пытается прерывать процессы, полученные с помощью командлета Get-proc (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена. Поскольку этот командлет останавливает системные процессы, он использует команду Stop, определенную классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , с существительным "proc" для обозначения процесса. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Следующий код является определением класса для этого командлета "останавливает-proc".

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

Командлету необходимо определить параметры, которые поддерживают изменения системы и отзывы пользователей. Командлет должен определить `Name` параметр или эквивалент, чтобы командлет мог изменять систему с помощью некоторого идентификатора. Кроме того, командлет должен определить `Force` `PassThru` Параметры и. Дополнительные сведения об этих параметрах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="defining-a-parameter-alias"></a>Определение псевдонима параметра

Псевдонимом параметра может быть альтернативное имя или четко определенное имя в виде одной или двух букв для параметра командлета. В обоих случаях цель использования псевдонимов — упростить ввод пользователя из командной строки. Windows PowerShell поддерживает псевдонимы параметров с помощью атрибута [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) , который использует синтаксис объявления [Alias ()].

В следующем коде показано, как псевдоним добавляется в `Name` параметр.

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

Помимо использования атрибута [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) , среда выполнения Windows PowerShell выполняет частичное совпадение имен, даже если псевдонимы не указаны. Например, если у командлета есть `FileName` параметр, который является единственным параметром, начинающимся с `F` , пользователь может ввести `Filename` , `Filenam` , `File` , `Fi` или `F` и по-прежнему распознать запись в качестве `FileName` параметра.

## <a name="creating-help-for-parameters"></a>Создание справки для параметров

Windows PowerShell позволяет создавать справку для параметров командлета. Это можно сделать для любого параметра, используемого для изменения системы и отзывов пользователей. Для каждого параметра, поддерживающего справку, можно задать `HelpMessage` ключевое слово Attribute в объявлении атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) . Это ключевое слово определяет текст, отображаемый пользователю для помощи в использовании параметра. Можно также задать `HelpMessageBaseName` ключевое слово, чтобы определить базовое имя ресурса, используемого для сообщения. Если задать это ключевое слово, необходимо также задать `HelpMessageResourceId` ключевое слово, чтобы указать идентификатор ресурса.

Следующий код из командлета «The-proc» определяет `HelpMessage` ключевое слово атрибута для `Name` параметра.

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Командлет должен переопределять метод обработки ввода, чаще всего это будет [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). При изменении системы командлет должен вызвать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , чтобы разрешить пользователю оставлять отзывы до внесения изменений. Дополнительные сведения об этих методах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="supporting-wildcard-expansion"></a>Поддержка расширения подстановочных знаков

Чтобы разрешить выбор нескольких объектов, командлет может использовать классы [System. Management. Automation. вилдкардпаттерн](/dotnet/api/System.Management.Automation.WildcardPattern) и [System. Management. Automation. вилдкардоптионс](/dotnet/api/System.Management.Automation.WildcardOptions) для предоставления поддержки расширения подстановочных знаков для ввода параметров. Примеры шаблонов с подстановочными знаками: LSA *, \* . txt и [a-c] \* . Используйте символ обратной кавычки (') в качестве escape-символа, если шаблон содержит символ, который следует использовать буквально.

Расширения с подстановочными знаками имен файлов и путей — это примеры распространенных сценариев, в которых командлет может разрешить ввод пути, если требуется выбрать несколько объектов. Общий случай — в файловой системе, где пользователь хочет просмотреть все файлы, находящиеся в текущей папке.

Необходимо использовать специальную реализацию шаблона с подстановочным знаком только в редких случаях. В этом случае командлет должен поддерживать полную спецификацию POSIX 1003,2, 3,13 для расширения с подстановочными знаками или следующее упрощенное подмножество:

- **Вопросительный знак (?).** Соответствует любому символу в указанном расположении.

- **Звездочка ( \* ).** Соответствует нулю или большему числу символов, начиная с указанного места.

- **Открывающая скобка ([).** Представляет выражение шаблонной скобки, которое может содержать символы или диапазон символов. Если диапазон является обязательным, для обозначения диапазона используется дефис (-).

- **Закрывающая квадратная скобка (]).** Завершает выражение шаблонной скобки.

- **Escape-символ обратной кавычки (').** Указывает, что следующий символ должен использоваться буквально. Имейте в виду, что при указании символа обратной кавычки из командной строки (в отличие от программного указания) escape-символ обратной кавычки должен быть указан дважды.

> [!NOTE]
> Дополнительные сведения о шаблонах с подстановочными знаками см. [в разделе Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).

В следующем коде показано, как задать подстановочные знаки и определить шаблон, используемый для разрешения `Name` параметра для этого командлета.

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

В следующем коде показано, как проверить, соответствует ли имя процесса определенному шаблону шаблона. Обратите внимание, что в этом случае, если имя процесса не соответствует шаблону, командлет продолжит процедуру, чтобы получить имя следующего процесса.

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a>Образец кода

Полный пример кода на C# см. в разделе [StopProcessSample03 Sample](./stopprocesssample03-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке. Давайте протестируем пример командлета "останавливает-proc". Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Запустите Windows PowerShell и используйте командлет "останавливает-обработать", чтобы прерывать процесс с помощью псевдонима ProcessName для `Name` параметра.

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

    Появится следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- В командной строке выполните следующую команду. Так как параметр name является обязательным, вам будет предложено ввести его. Ввод "!?" выводит текст справки, связанный с параметром.

    ```powershell
    PS> stop-proc
    ```

    Появится следующий результат.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- Теперь выполните следующую запись, чтобы отключить все процессы, соответствующие шаблону подстановочного знака "* Note \* ". Перед остановкой каждого процесса, соответствующего шаблону, выводится запрос.

    ```powershell
    PS> stop-proc -Name *note*
    ```

    Появится следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

    Появится следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

    Появится следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также

[Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md)

[Создание командлета Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
