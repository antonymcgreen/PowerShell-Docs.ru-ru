---
title: Добавление параметров, обрабатывающих входные данные конвейера | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programmer's Guide], pipeline input
ms.openlocfilehash: a678df30a13086b317d5680ee0fbc4d3c3391235
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784560"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>Добавление параметров для обработки входных данных конвейера

Один источник входных данных для командлета — это объект в конвейере, исходящий из вышестоящего командлета. В этом разделе описывается, как добавить параметр в командлет Get-proc (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)), чтобы командлет мог обрабатывать объекты конвейера.

Этот командлет Get-proc использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.

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

В этом разделе описывается, как определить входные данные из конвейера для командлета. Этот командлет Get-proc определяет свойство, представляющее `Name` параметр, как описано в разделе [Добавление параметров, обрабатывающих вход командной строки](./adding-parameters-that-process-command-line-input.md).
(Общие сведения об объявлении параметров см. в этом разделе.)

Однако если командлету необходимо обработать входные данные конвейера, он должен быть привязан к входным значениям среды выполнения Windows PowerShell. Для этого необходимо добавить `ValueFromPipeline` ключевое слово или добавить `ValueFromPipelineByProperty` ключевое слово в объявление атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) . Укажите `ValueFromPipeline` ключевое слово, если командлет обращается к полному входному объекту. Укажите, `ValueFromPipelineByProperty` Если командлет обращается только к свойству объекта.

Ниже приведено объявление параметра для `Name` параметра командлета Get-proc, принимающего входные данные конвейера.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

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

В предыдущем объявлении ключевому слову присваивается значение, чтобы `ValueFromPipeline` `true` Среда выполнения Windows PowerShell привязать параметр к входящему объекту, если объект имеет тот же тип, что и параметр, или если он может быть приведен к тому же типу. `ValueFromPipelineByPropertyName`Ключевое слово также имеет значение, чтобы `true` Среда выполнения Windows PowerShell проверит входящий объект для `Name` Свойства. Если входящий объект имеет такое свойство, среда выполнения привязывает `Name` параметр к `Name` свойству входящего объекта.

> [!NOTE]
> Значение `ValueFromPipeline` ключевого слова атрибута для параметра имеет приоритет над параметром `ValueFromPipelineByPropertyName` ключевого слова.

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Если командлет обрабатывает входные данные конвейера, необходимо переопределить соответствующие методы обработки входных данных. Основные методы обработки ввода представлены при [создании первого командлета](./creating-a-cmdlet-without-parameters.md).

Этот командлет Get-proc переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для управления `Name` входными параметрами, предоставленными пользователем или сценарием. Этот метод получит процессы для каждого запрошенного имени процесса или всех процессов, если имя не указано. Обратите внимание, что в [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)вызов [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) является механизмом вывода для отправки выходных объектов в конвейер. Второй параметр этого вызова, `enumerateCollection` ,, имеет значение, чтобы `true` сообщить среде выполнения Windows PowerShell о необходимости перечисления массива объектов процессов и записывать в командную строку один процесс.

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

Полный пример кода на C# см. в разделе [GetProcessSample03 Sample](./getprocesssample03-sample.md).

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

  Появится следующий результат.

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- Введите следующие строки, чтобы получить объекты процесса со `Name` свойством из процессов с именем "iexplore". В этом примере используется `Get-Process` командлет (предоставленный Windows PowerShell) в качестве вышестоящей команды для получения процессов iexplore.

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  Появится следующий результат.

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a>См. также

[Добавление параметров, обрабатывающих вход командной строки](./adding-parameters-that-process-command-line-input.md)

[Создание первого командлета](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
