---
title: Добавление в командлет незавершающего сообщения об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: a4426abec96cd922360aeef8c157b4e9f41a15b9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364613"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a>Добавление сообщения о непрерывающей ошибке в командлет

Командлеты могут сообщать о неустранимых ошибках, вызывая метод [System. Management. Automation. командлет. WriteError][] и продолжая работать с текущим входным объектом или с дальнейшими входящими объектами конвейера.
В этом разделе объясняется, как создать командлет, сообщающий о неустранимых ошибках из своих методов обработки входных данных.

Для неустранимых ошибок (а также для прерывания ошибок) командлет должен передать объект [System. Management. Automation. ерроррекорд][] , определяющий ошибку.
Каждая запись об ошибке идентифицируется уникальной строкой с именем "Идентификатор ошибки".
В дополнение к идентификатору Категория каждой ошибки задается константами, определенными перечислением [System. Management. Automation. ErrorCategory][] .
Пользователь может просматривать ошибки на основе их категории, присвоив переменной `$ErrorView` значение "Категоривиев".

Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.
Этот командлет извлекает сведения о процессе, поэтому выбранное здесь имя команды — Get.
(Практически любой командлет, который способен получить информацию, может обрабатывать входные данные командной строки.) Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение для командлета Get-proc.
Подробные сведения об этом определении приведены в [создании первого командлета](creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a>Определение параметров

При необходимости командлет должен определить параметры для обработки входных данных.
Этот командлет Get-proc определяет параметр **Name** , как описано в разделе [Добавление параметров, обрабатывающих вход командной строки](adding-parameters-that-process-command-line-input.md).

Ниже приведено объявление параметра для параметра **Name** командлета Get-proc.

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

## <a name="overriding-input-processing-methods"></a>Переопределение методов обработки входных данных

Все командлеты должны переопределять по крайней мере один из методов обработки ввода, предоставляемых классом [System. Management. Automation. командлет][] .
Эти методы обсуждаются в разделе [Создание первого командлета](creating-a-cmdlet-without-parameters.md).

> [!NOTE]
> Командлет должен обрабатывать каждую запись как можно независимо.

Этот командлет Get-proc переопределяет метод [System. Management. Automation. командлет. ProcessRecord][] для работы с параметром **Name** для входных данных, предоставленных пользователем или сценарием.
Этот метод получит процессы для каждого запрошенного имени процесса или всех процессов, если имя не указано.
Сведения об этом переопределении приведены в [создании первого командлета](creating-a-cmdlet-without-parameters.md).

### <a name="things-to-remember-when-reporting-errors"></a>Вопросы, которые следует помнить при сообщении об ошибках

Объект [System. Management. Automation. ерроррекорд][] , который передается командлетом при записи ошибки, требует возникновения исключения в ядре.
При определении используемого исключения следуйте рекомендациям .NET.
В основном, если ошибка семантически аналогична существующему исключению, командлет должен использовать или наследовать его от этого исключения.
В противном случае он должен создать новое исключение или иерархию исключений непосредственно из класса [System. Exception][] .

При создании идентификаторов ошибок (доступ к которым осуществляется через свойство Фулликуалифиедеррорид класса Ерроррекорд) учитывайте следующее.

- Используйте строки, предназначенные для диагностики, чтобы при проверке полного идентификатора можно было определить причину ошибки и источник ошибки.

- Правильно сформированный полный идентификатор ошибки может выглядеть следующим образом.

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

Обратите внимание, что в предыдущем примере идентификатор ошибки (первый маркер) обозначает, что такое ошибка, а оставшаяся часть указывает, откуда поступила ошибка.

- Для более сложных сценариев Идентификатор ошибки может быть маркером, разделенным точкой, который может быть проанализирован при проверке.
  Это позволяет создать ветвь для частей идентификатора ошибки, а также идентификатор ошибки и категорию ошибки.

Командлет должен назначить определенные идентификаторы ошибок различным путям кода.
При назначении идентификаторов ошибок учитывайте следующие сведения:

- Идентификатор ошибки должен оставаться постоянным в течение жизненного цикла командлета.
  Не изменяйте семантику идентификатора ошибки между версиями командлетов.

- Используйте текст для идентификатора ошибки, который кратко соответствует сообщению об ошибке.
  Не используйте пробелы или знаки препинания.

- Создайте командлет, который создает только воспроизводимые идентификаторы ошибок.
  Например, он не должен создавать идентификатор, включающий идентификатор процесса.
  Идентификаторы ошибок полезны для пользователя только в том случае, если они соответствуют идентификаторам, которые видят другие пользователи, испытывающие ту же проблему.

Необработанные исключения не перехватываются PowerShell в следующих случаях:

- Если командлет создает новый поток и код, выполняющийся в этом потоке, создает необработанное исключение, PowerShell не будет перехватывать ошибку и завершит процесс.

- Если у объекта есть код в его деструкторе или методы Dispose, вызывающие необработанное исключение, PowerShell не будет перехватывать ошибку и завершит процесс.

## <a name="reporting-nonterminating-errors"></a>Сообщает о неустранимых ошибках

Любой из методов обработки входных данных может сообщить о неустранимой ошибке в поток вывода с помощью метода [System. Management. Automation. командлет. WriteError][] .

Ниже приведен пример кода из этого командлета Get-proc, который иллюстрирует вызов [System. Management. Automation. командлет. WriteError][] из переопределения метода [System. Management. Automation. командлет. ProcessRecord][] .
В этом случае вызов выполняется, если командлет не может найти процесс для указанного идентификатора процесса.

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a>Важные сведения о написании неустранимых ошибок

Для незавершающей ошибки командлет должен создать конкретный идентификатор ошибки для каждого конкретного входного объекта.

Командлету часто требуется изменить действие PowerShell, созданное неустранимой ошибкой.
Это можно сделать, определив параметры `ErrorAction` и `ErrorVariable`.
При определении параметра `ErrorAction` командлет представляет пользовательские параметры [System. Management. Automation. действие][], и вы можете напрямую повлиять на действие, задав переменную `$ErrorActionPreference`.

Командлет может сохранять неустранимые ошибки в переменной с помощью параметра `ErrorVariable`, который не зависит от значения параметра `ErrorAction`.
Ошибки можно добавить к существующей переменной ошибки, добавив знак «плюс» (+) перед именем переменной.

## <a name="code-sample"></a>Образец кода

Полный C# пример кода см. в разделе [GetProcessSample04 Sample](./getprocesssample04-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирование

PowerShell передает сведения между командлетами с помощью объектов .NET.
Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.
Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell.
Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в PowerShell, его можно проверить, запустив его в командной строке.
Давайте проверим пример командлета Get-proc, чтобы проверить, сообщает ли он об ошибке:

- Запустите PowerShell и используйте командлет Get-proc, чтобы получить процессы с именем TEST.

    ```powershell
    PS> get-proc -name test
    ```

Появится следующий вывод.

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a>См. также:

[Добавление параметров, обрабатывающих входные данные конвейера](./adding-parameters-that-process-pipeline-input.md)

[Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md)

[Создание первого командлета](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)

[System. Exception]: /dotnet/api/System.Exception
[System. Management. Automation. действие]: /dotnet/api/System.Management.Automation.ActionPreference
[System. Management. Automation. командлет. ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System. Management. Automation. командлет. WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Management. Automation. командлет]: /dotnet/api/System.Management.Automation.Cmdlet
[System. Management. Automation. ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System. Management. Automation. Ерроррекорд]: /dotnet/api/System.Management.Automation.ErrorRecord
