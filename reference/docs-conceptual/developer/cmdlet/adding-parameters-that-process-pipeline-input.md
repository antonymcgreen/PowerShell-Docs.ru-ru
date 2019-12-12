---
title: Добавление параметров, обрабатывающих входные данные конвейера | Документация Майкрософт
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
ms.openlocfilehash: 9ecb73a4138a5853fa5fb378874da2d81c5dbdba
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364603"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>Добавление параметров для обработки входных данных конвейера

Один источник входных данных для командлета — это объект в конвейере, исходящий из вышестоящего командлета. В этом разделе описывается, как добавить параметр в командлет Get-proc (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)), чтобы командлет мог обрабатывать объекты конвейера.

Этот командлет Get-proc использует параметр `Name`, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.

## <a name="defining-the-cmdlet-class"></a>Определение класса командлета

Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет. Этот командлет извлекает сведения о процессе, поэтому выбранное здесь имя команды — Get. (Практически любой командлет, который способен получить информацию, может обрабатывать входные данные командной строки.) Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

Ниже приведено определение для командлета Get-proc. Подробные сведения об этом определении приведены в [создании первого командлета](./creating-a-cmdlet-without-parameters.md).

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

В этом разделе описывается, как определить входные данные из конвейера для командлета. Этот командлет Get-proc определяет свойство, представляющее параметр `Name`, как описано в разделе [Добавление параметров, обрабатывающих вход командной строки](./adding-parameters-that-process-command-line-input.md). (Общие сведения об объявлении параметров см. в этом разделе.)

Однако если командлету необходимо обработать входные данные конвейера, он должен быть привязан к входным значениям среды выполнения Windows PowerShell. Для этого необходимо добавить ключевое слово `ValueFromPipeline` или добавить ключевое слово `ValueFromPipelineByProperty` в объявление атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) . Укажите ключевое слово `ValueFromPipeline`, если командлет обращается к полному входному объекту. Укажите `ValueFromPipelineByProperty`, если командлет обращается только к свойству объекта.

Ниже приведено объявление параметра для параметра `Name` командлета Get-proc, принимающего входные данные конвейера.

[!code-csharp[GetProcessSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

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

В предыдущем объявлении ключевому слову `ValueFromPipeline` присваивается значение `true`, чтобы среда выполнения Windows PowerShell привязать параметр к входящему объекту, если объект имеет тот же тип, что и параметр, или, если он может быть приведен к тому же типу. Ключевое слово `ValueFromPipelineByPropertyName` также имеет значение `true`, чтобы среда выполнения Windows PowerShell проверит входящий объект на наличие свойства `Name`. Если входящий объект имеет такое свойство, среда выполнения привязывает параметр `Name` к свойству `Name` входящего объекта.

> [!NOTE]
> Значение ключевого слова `ValueFromPipeline` атрибута для параметра имеет приоритет над параметром ключевого слова `ValueFromPipelineByPropertyName`.

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Если командлет обрабатывает входные данные конвейера, необходимо переопределить соответствующие методы обработки входных данных. Основные методы обработки ввода представлены при [создании первого командлета](./creating-a-cmdlet-without-parameters.md).

Этот командлет Get-proc переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для управления входными параметрами `Name`, предоставленными пользователем или сценарием. Этот метод получит процессы для каждого запрошенного имени процесса или всех процессов, если имя не указано. Обратите внимание, что в [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)вызов [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) является механизмом вывода для отправки выходных объектов в конвейер. Второй параметр этого вызова, `enumerateCollection`, имеет значение `true`, чтобы сообщить среде выполнения Windows PowerShell о необходимости перечисления массива объектов процессов и записывать один процесс в командную строку.

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

## <a name="code-sample"></a>Образец кода

Полный C# пример кода см. в разделе [GetProcessSample03 Sample](./getprocesssample03-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

После регистрации командлета в Windows PowerShell проверьте его, запустив в командной строке. Например, протестируйте код для примера командлета. Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- В командной строке Windows PowerShell введите следующие команды, чтобы получить имена процессов через конвейер.

    ```powershell
    PS> type ProcessNames | get-proc
    ```

Появится следующий вывод.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- Введите следующие строки, чтобы получить объекты процесса со свойством `Name` из процессов с именем "IEXPLORE". В этом примере используется командлет `Get-Process` (предоставляемый Windows PowerShell) в качестве вышестоящей команды для получения процессов "IEXPLORE".

    ```powershell
    PS> get-process iexplore | get-proc
    ```

Появится следующий вывод.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a>См. также:

[Добавление параметров, обрабатывающих вход командной строки](./adding-parameters-that-process-command-line-input.md)

[Создание первого командлета](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
