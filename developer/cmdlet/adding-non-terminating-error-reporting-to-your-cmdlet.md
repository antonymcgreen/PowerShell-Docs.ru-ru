---
title: Добавление устранимую командлета отчетов об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: e0550dacc33f45f45ba105ca5cb4d2e5b5d675fb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056062"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a>Добавление сообщения о непрерывающей ошибке в командлет

Командлеты можно сообщить устранимые ошибки путем вызова [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метода и продолжить работу на текущий входной объект или на Дополнительные Входящие конвейер объектов. В этом разделе объясняется, как создать командлет, который сообщает устранимые ошибки из его методов обработки ввода.

Устранимые ошибки (а также прерывающие ошибки), командлет необходимо передать [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объект, определяющий ошибку. Каждая ошибка запись идентифицируется по уникальной строки, называемой «идентификатор ошибка». Кроме идентификатора категории каждой ошибки определяется константы, определенные в [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory) перечисления. Пользователь может просмотреть ошибки, на основе их категории, установив `$ErrorView` переменной «CategoryView».

Дополнительные сведения о записи об ошибках, см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

Следующие подразделы этого раздела.

- [Определение командлета](#Defining-the-Cmdlet)

- [Определение параметров](#Defining-Parameters)

- [Переопределяя методы обработки ввода](#Overriding-Input-Processing-Methods)

- [Устранимые ошибки](#Reporting-Nonterminating-Errors)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование](#Define-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a>Определение командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get». (Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение для этого командлета Get-Proc. Сведения из этого определения приведены [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

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

При необходимости в командлете необходимо определить параметры для обработки входных данных. Этот командлет Get-Proc определяет `Name` параметра, как описано в разделе [Добавление параметров командной строки этого процесса входа](./adding-parameters-that-process-command-line-input.md).

Ниже приведено объявление параметра для `Name` из параметров командлета Get-Proc.

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

## <a name="overriding-input-processing-methods"></a>Переопределяя методы обработки ввода

Все командлеты необходимо переопределить хотя бы один из методов, предоставляемых обработки ввода [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса. Эти методы описаны в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

> [!NOTE]
> Командлет для независимой обработки каждой записи.

Этот командлет Get-Proc переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки `Name` параметр для входных данных, предоставленных пользователю или сценарий. Этот метод будет получения процессов для каждого имени запрошенного процесса и всех процессов, если имя не указано. Сведения о это переопределение приведены в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

#### <a name="things-to-remember-when-reporting-errors"></a>О чем следует помнить при сообщении об ошибках

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта, что командлет передает при записи ошибки требует исключение по своей сути. Следуйте рекомендациям .NET, при определении исключение для использования. По сути Если ошибка является семантически так же, как существующие исключения, этот командлет следует использовать, или являются производными от этого исключения. В противном случае он должен быть производным новое исключение, либо иерархия исключений непосредственно из [System.Exception](/dotnet/api/System.Exception) класса.

При создании ошибки идентификаторы (через свойство FullyQualifiedErrorId класса ErrorRecord) Имейте в виду следующее.

- Использование строк, которые предназначены для диагностики, чтобы при проверке полный идентификатор можно определить, какие ошибки — и там, где ошибка возникла.

- Идентификатор корректность полное ошибка может выглядеть следующим образом.

`CommandNotFoundException,Micrososft.PowerShell.Commands.GetCommanddCommand.`

Обратите внимание на то, что в предыдущем примере, код ошибки (первый токен) обозначает ошибку, а оставшиеся части показывает происхождения ошибки.

- Для более сложных сценариев код ошибки может быть маркер точки с запятыми, который может быть проанализирован для проверки. Это позволяет слишком ветви на тех частях идентификатор ошибки, а также идентификатор и ошибка категорию ошибки.

Командлет следует назначить конкретной ошибке идентификаторы разных путей кода. Учитывайте следующие сведения для назначения идентификаторов, ошибка:

- Идентификатор ошибки должны оставаться неизменным на протяжении всего жизненного цикла командлета. Не изменяет семантику идентификатора ошибка между версиями командлет.

- Используйте текст ошибки идентификатор, который соответствует кратко сообщение об ошибке. Не используйте пробелы или знаки препинания.

- У командлета создавать только идентификаторы ошибки, воспроизводимый. Например она не должна создавать идентификатор, который включает идентификатор процесса. Ошибка идентификаторы полезны пользователю только в том случае, если они соответствуют идентификаторы, которые будут видны другим пользователям, столкнувшимся с этой проблемы.

Необработанные исключения не перехватываются Windows PowerShell в следующих ситуациях:

- Если командлет создает новый поток и код, выполняемый в том, что поток вызывает необработанное исключение, Windows PowerShell не перехватывает ошибку и завершает процесс.

- Если объект имеет код в его деструктор или метод Dispose, который приводит к возникновению необработанного исключения, Windows PowerShell не перехватывает ошибку и завершает процесс.

## <a name="reporting-nonterminating-errors"></a>Устранимые ошибки

Один из методов обработки ввода, может сообщать устранимые ошибки в поток вывода с помощью [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод. Ниже приведен пример кода из этого демонстрируется вызов командлета Get-Proc [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из в переопределенной [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод. В этом случае вызов выполняется, если командлет не удается найти процесс для идентификатора указанного процесса.

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

#### <a name="things-to-remember-about-writing-nonterminating-errors"></a>О чем следует помнить о написании устранимые ошибки

Устранимые ошибки командлет необходимо создать идентификатор конкретной ошибки для каждого конкретного входного объекта.

Командлет часто необходимо изменить действие Windows PowerShell, созданные устранимые ошибки. Можно сделать путем определения `ErrorAction` и `ErrorVariable` параметров. Если определение `ErrorAction` параметр, командлет представлены параметры пользователя [System.Management.Automation.Actionpreference](/dotnet/api/system.management.automation.actionpreference), можно также непосредственно влияют на действие, задав `$ErrorActionPreference` переменной.

Командлет можно сохранить устранимые ошибки в переменной с помощью `ErrorVariable` параметр, который не зависит от параметра `ErrorAction`. Сбои можно добавить в существующую переменную ошибки, добавив знак плюс (+) в начале имени переменной.

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример GetProcessSample04](./getprocesssample04-sample.md).

## <a name="define-object-types-and-formatting"></a>Определение типов объектов и форматирования

Windows PowerShell передает данные между командлетами, используя объекты .NET. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке. Давайте протестируем командлету Get-Proc пример см. в разделе ли она сообщает об ошибке:

- Запустите Windows PowerShell и используйте командлет Get-Proc для получения процессов, с именем «TEST».

    ```powershell
    PS> get-proc -name test
    ```

Появляется следующий результат.

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a>См. также

[Добавление параметров конвейера обработки входных данных](./adding-parameters-that-process-pipeline-input.md)

[Добавление параметров, которые обрабатывают данные в командной строке](./adding-parameters-that-process-command-line-input.md)

[Создайте свой первый командлет](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
