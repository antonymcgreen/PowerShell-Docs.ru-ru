---
title: Добавление параметров, которые обрабатывают входные данные конвейера | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programmer's Guide], pipeline input
ms.assetid: 09bf70a9-7c76-4ffe-b3f0-a1d5f10a0931
caps.latest.revision: 8
ms.openlocfilehash: bd52dc8aee7975d0899083a5c2f595b17690dc33
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068765"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>Добавление параметров для обработки входных данных конвейера

Один источник входных данных для командлета — это объект в конвейер, поступающие из вышестоящего командлет. В этом разделе описывается добавление параметра в командлет Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)), чтобы командлет может обрабатывать объекты конвейера.

Этот командлет Get-Proc использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе на локальном компьютере, на основе предоставленных имен и затем отображает сведения о процессах в командной строке.

Следующие подразделы этого раздела.

- [Определение класса командлета](#Defining-the-Cmdlet-Class)

- [Определение входных данных из конвейера](#Defining-Input-from-the-Pipeline)

- [Переопределив метод обработки входных данных](#Overriding-an-Input-Processing-Method)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование](#Defining-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a>Определение класса командлета

Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет. Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get». (Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение для этого командлета Get-Proc. Сведения из этого определения приведены [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a>Определение входных данных из конвейера

В этом разделе описывается определение входных данных из конвейера для командлета. Этот командлет Get-Proc определяет свойство, которое представляет `Name` параметра, как описано в разделе [Добавление параметров командной строки этого процесса входа](./adding-parameters-that-process-command-line-input.md). (См. разделе Общие сведения об объявлении параметров).

Тем не менее если командлет должен обрабатывать входные данные конвейера, он должен иметь его параметры, привязанные к входных значений средой выполнения Windows PowerShell. Чтобы сделать это, необходимо добавить `ValueFromPipeline` ключевое слово или добавить `ValueFromPipelineByProperty` слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута. Укажите `ValueFromPipeline` ключевое слово, если командлет осуществляет доступ к завершения входного объекта. Укажите `ValueFromPipelineByProperty` если командлет подключается только к свойству объекта.

Ниже приведено объявление параметра для `Name` параметр этого командлета Get-Proc, которая принимает входные данные конвейера.

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

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

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

Предыдущие объявления наборы `ValueFromPipeline` ключевое слово `true` среды выполнения Windows PowerShell будет привязать параметр к входящего объекта, если объект совпадает с типом параметра, или, если он может быть преобразован в один тип. `ValueFromPipelineByPropertyName` Ключевого слова задано также `true` таким образом, чтобы среда выполнения Windows PowerShell будет проверять входящего объекта для `Name` свойство. Если входящий объект имеет такое свойство, среда выполнения будет привязан `Name` параметр `Name` свойства входящего объекта.

> [!NOTE]
> Параметр `ValueFromPipeline` атрибут ключевого слова для параметра имеет приоритет над параметром для `ValueFromPipelineByPropertyName` ключевое слово.

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

Если командлет должен обрабатывать входные данные конвейера, ему необходимо переопределить соответствующие методы обработки ввода. Методы базовую обработку ввода, использованные в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

Этот командлет Get-Proc переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки `Name` входные параметры, предоставляемые пользователем или сценарий. Этот метод будет получения процессов для каждого имени запрошенного процесса и всех процессов, если имя не указано. Обратите внимание, что в [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), вызов [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) выходные данные механизм для отправки выходных данных объекты в конвейер. Второй параметр этой вызов `enumerateCollection`, имеет значение `true` сообщить среде выполнения Windows PowerShell для перечисления массива объектов процессов и один процесс записи за раз в командную строку.

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример GetProcessSample03](./getprocesssample03-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает данные между командлетами, используя объекты .net. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета он зарегистрирован с помощью Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

Если командлет зарегистрирован с помощью Windows PowerShell, проверьте его, запустив его в командной строке. Например можно тестировать код для командлета пример. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- В командной строке Windows PowerShell введите следующие команды, чтобы получить имена процессов по конвейеру.

    ```powershell
    PS> type ProcessNames | get-proc
    ```

Появляется следующий результат.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- Введите следующие строки, чтобы получить объекты процессов, имеющих `Name` свойство с процессами, которые называются «IEXPLORE». В этом примере используется `Get-Process` командлет (предоставляемое Windows PowerShell), как вышестоящий команду для получения процессов «IEXPLORE».

    ```powershell
    PS> get-process iexplore | get-proc
    ```

Появляется следующий результат.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a>См. также

[Добавление параметров, которые обрабатывают входные данные командной строки](./adding-parameters-that-process-command-line-input.md)

[Создайте свой первый командлет](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
