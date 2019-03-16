---
title: Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: db664e589f625855b5a33a02c522d6b238ad2810
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054887"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a>Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета

В этом разделе описывается добавление псевдонимы, развертывание знаков подстановки, и сообщения справки для параметров командлета Stop-Proc (описано в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md)).

Этот командлет Stop-Proc пытается остановить процессы, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)).

Следующие подразделы этого раздела.

- [Определение командлета](#Defining-the-Cmdlet)

- [Определение параметров для изменения системы](#Defining-Parameters-for-System-Modification)

- [Определение псевдоним параметра](#Defining-a-Parameter-Alias)

- [Создание справки для параметров](#Creating-Help-for-Parameters)

- [Переопределив метод обработки входных данных](#Overriding-an-Input-Processing-Method)

- [Поддержка подстановочных знаков](#Supporting-Wildcard-Expansion)

- [Пример кода](#Defining-a-Parameter-Alias)

- [Определение типов объектов и форматирование](#Define-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Так как вы записываете командлета для изменения системы, его имя должно соответствующим образом. Так как этот командлет останавливает системные процессы, используется команда «Stop», определяемый [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) класс с существительным «Proc», чтобы указать процесс. Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Следующий код является определение класса для этого командлета Stop-Proc.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a>Определение параметров для изменения системы

Командлет необходимо определить параметры, что изменения системы поддержки и отзывы пользователей. Командлет необходимо определить `Name` параметр или эквивалент, чтобы командлет, смогут изменять параметры системы в каком-то идентификатора. Кроме того, следует определить командлет `Force` и `PassThru` параметров. Дополнительные сведения об этих параметрах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="defining-a-parameter-alias"></a>Определение псевдоним параметра

Псевдоним параметра может быть альтернативное имя или четко определенных буква 1 или 2-буква короткое имя для параметра командлета. В обоих случаях использования псевдонимов призван упростить ввод пользователя из командной строки. Windows PowerShell поддерживает псевдонимы параметра с помощью [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) атрибут, который использует синтаксис объявления [Alias()].

В следующем коде показано, как добавляется псевдоним `Name` параметра.

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

Помимо использования [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) атрибутов, среда выполнения Windows PowerShell выполняет частичное сопоставление имен, даже если псевдонимы не указаны. Например, если есть командлет `FileName` параметр и это единственный параметр, который начинается с `F`, пользователь может вводить `Filename`, `Filenam`, `File`, `Fi`, или `F` и по-прежнему распознавания записи в виде `FileName` параметра.

## <a name="creating-help-for-parameters"></a>Создание справки для параметров

Windows PowerShell позволяет создать справки для параметров командлета. Это необходимо сделайте для любого параметра, используемое для изменения и сбора отзывов системы. Для каждого параметра, для поддержки справки, можно задать `HelpMessage` атрибута ключевое слово в [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута. Это ключевое слово определяет текст, отображаемый пользователю для помощи в с помощью параметра. Можно также задать `HelpMessageBaseName` ключевое слово, чтобы определить базовое имя ресурса будет использоваться для сообщения. Если это ключевое слово, необходимо также задать `HelpMessageResourceId` ключевое слово, чтобы указать идентификатор ресурса.

Следующий код из этого командлета Stop-Proc определяет `HelpMessage` ключевое слово для атрибута `Name` параметра.

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

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

Командлет необходимо переопределить метод обработки входных данных, чаще всего это будет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord). При изменении в системе, следует вызвать командлет [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, позволяющие пользователю Чтобы оставить отзыв, прежде чем изменения. Дополнительные сведения об этих методах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).

## <a name="supporting-wildcard-expansion"></a>Поддержка подстановочных знаков

Чтобы разрешить выбор нескольких объектов, можно использовать командлет [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) и [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) классам предоставлять Поддержка расширения подстановочный знак для входного параметра. Примеры шаблонов с подстановочными знаками — lsa * \*txt и [a-c]\*. Используйте символ обратной кавычки (') как escape-символ, если шаблон содержит символ, который должен использоваться буквально.

Подстановочный знак расширения имен файлов и путь приведены примеры распространенных сценариев, где командлета может потребоваться предоставить для входных данных путь к службе технической поддержки при необходимости выделения нескольких объектов. Распространенным вариантом является в файловой системе, где пользователь хочет видеть все файлы, находящиеся в текущей папке.

Реализацию соответствующий шаблон настроенный шаблон нужен лишь изредка. В этом случае командлет должен поддерживать полный 1003.2 POSIX, 3,13 спецификации для подстановочных знаков или Следующий упрощенный набор:

- **Вопросительный знак (?).** Соответствует любому символу в указанном расположении.

- **Звездочка (\*).** Совпадает с нуля или более символов, начиная с указанной позиции.

- **Открывающая скобка ([]).** Представляет выражение в квадратных скобках шаблон, содержащий символы или диапазона символов. Если требуется диапазон, дефис (-) используется для указания диапазона.

- **Закрывающая скобка (]).** Завершает выражение в квадратных скобках шаблон.

- **Обратной кавычки escape-символ (').** Указывает, что следующий символ должен восприниматься буквально. Имейте в виду, что при указании символ обратной кавычки из командной строки (в отличие от указания программным способом), обратной кавычки escape-символа должно быть указано два раза.

> [!NOTE]
> Дополнительные сведения о шаблоны с подстановочными знаками, см. в разделе [Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).

Ниже показано, как настроить параметры шаблонов и определить шаблон подстановочного знака, используемую для разрешения `Name` параметр для этого командлета.

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

Приведенный ниже показано, как для проверки того, соответствует ли имя процесса определенный шаблон. Обратите внимание на то, что, в этом случае, если имя процесса не соответствует шаблону, командлет продолжает на получить имя следующего процесса.

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример StopProcessSample03](./stopprocesssample03-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирования

Windows PowerShell передает данные между командлетами, используя объекты .net. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, его необходимо зарегистрировать с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке. Давайте протестируем командлет Stop-Proc образец. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Запустите Windows PowerShell и используйте Stop-Proc остановить процесс, использующий ProcessName псевдоним `Name` параметра.

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

Появляется следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Создайте следующую запись в командной строке. Так как параметр Name является обязательным, запросит его. Введите «!?» появится текст справки, связанный с параметром.

    ```powershell
    PS> stop-proc
    ```

Появляется следующий результат.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- Теперь создайте следующую запись, чтобы остановить все процессы, которые соответствуют Шаблон подстановочного знака «* Примечание\*«. Вам предлагается перед остановкой каждого процесса, которая соответствует шаблону.

    ```powershell
    PS> stop-proc -Name *note*
    ```

Появляется следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

Появляется следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

Появляется следующий результат.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>См. также

[Создать командлет, который изменяет системы](./creating-a-cmdlet-that-modifies-the-system.md)

[Как создать командлет Windows PowerShell](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
