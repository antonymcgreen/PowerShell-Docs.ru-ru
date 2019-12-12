---
title: Создание командлета без параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: af41c2c9855310d047404114a07b27180a7aa8fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415675"
---
# <a name="creating-a-cmdlet-without-parameters"></a>Создание командлета без параметров

В этом разделе описывается создание командлета, который получает сведения с локального компьютера без использования параметров, а затем записывает сведения в конвейер. Описываемый здесь командлет является командлетом Get-proc, который получает сведения о процессах локального компьютера, а затем отображает эти сведения в командной строке.

> [!NOTE]
> Имейте в виду, что при написании командлетов ссылочные сборки® Windows PowerShell загружаются на диск (по умолчанию — C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0). Они не устанавливаются в глобальный кэш сборок (GAC).

## <a name="naming-the-cmdlet"></a>Присвоение имени командлету

Имя командлета состоит из глагола, указывающего действие, которое выполняет командлет, и существительное, которое указывает элементы, с которыми работает командлет. Так как этот пример командлета Get-proc извлекает объекты обработки, он использует команду Get, определенную перечислением [System. Management. Automation. вербскоммон](/dotnet/api/System.Management.Automation.VerbsCommon) , и существительное "proc", чтобы указать, что командлет работает с элементами процесса.

При именовании командлетов не используйте следующие символы: #, () {} [] &-/\ $; : "< > &#124; ? @ ` .

### <a name="choosing-a-noun"></a>Выбор существительного

Следует выбрать конкретное существительное. Лучше использовать одноименное существительное с сокращенной версией названия продукта. Примером имени командлета этого типа является "`Get-SQLServer`".

### <a name="choosing-a-verb"></a>Выбор команды

Следует использовать глагол из набора утвержденных имен глаголов командлетов. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).

## <a name="defining-the-cmdlet-class"></a>Определение класса командлета

После выбора имени командлета определите класс .NET для реализации командлета. Ниже приведено определение класса для этого примера командлета Get-proc:

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

Обратите внимание, что предыдущий с определением класса атрибут [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) с синтаксисом `[Cmdlet(verb, noun, ...)]`, используется для определения этого класса в качестве командлета. Это единственный обязательный атрибут для всех командлетов, позволяющий среде выполнения Windows PowerShell правильно вызывать их. При необходимости можно задать ключевые слова атрибутов для дальнейшего объявления класса. Обратите внимание, что объявление атрибута для нашего примера класса Жетпроккомманд объявляет только имена существительных и глаголов для командлета Get-proc.

> [!NOTE]
> Ключевые слова, которые можно задать для всех классов атрибутов Windows PowerShell, соответствуют свойствам класса Attribute.

При именовании класса командлета рекомендуется отразить имя командлета в имени класса. Для этого используйте форму "Вербнаункомманд" и замените "verb" и "существительное" на глагол и существительное, используемые в имени командлета. Как показано в предыдущем определении класса, пример командлета Get-proc определяет класс с именем Жетпроккомманд, производный от базового класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) .

> [!IMPORTANT]
> Если вы хотите определить командлет, который напрямую обращается к среде выполнения Windows PowerShell, класс .NET должен быть производным от базового класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) . Дополнительные сведения об этом классе см. [в разделе Создание командлета, определяющего наборы параметров](./adding-parameter-sets-to-a-cmdlet.md).

> [!NOTE]
> Класс для командлета должен быть явно помечен как открытый. Классы, которые не помечены как открытые, по умолчанию будут внутренними и не будут найдены средой выполнения Windows PowerShell.

Windows PowerShell использует пространство имен [Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) для своих классов командлетов. Рекомендуется размещать классы командлетов в пространстве имен Commands пространства имен API, например XXX. PS. Commands.

## <a name="overriding-an-input-processing-method"></a>Переопределение метода обработки входных данных

Класс [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) предоставляет три основных метода обработки ввода, по крайней мере один из которых должен переопределяться командлетом. Дополнительные сведения о том, как Windows PowerShell обрабатывает записи, см. в разделе [как работает Windows PowerShell](/previous-versions//ms714658(v=vs.85)).

Для всех типов входных данных среда выполнения Windows PowerShell вызывает [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) для включения обработки. Если командлет должен выполнить некоторую предварительную обработку или установку, это можно сделать, переопределив этот метод.

> [!NOTE]
> Windows PowerShell использует термин "запись" для описания набора значений параметров, предоставляемых при вызове командлета.

Если командлет принимает входные данные конвейера, он должен переопределить метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и, при необходимости, метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Например, командлет может переопределить оба метода, если он собирает все входные данные с помощью [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , а затем работает с входными данными как целым, а не по одному элементу за раз, как это делает командлет `Sort-Object`.

Если командлет не принимает входные данные конвейера, он должен переопределить метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Имейте в виду, что этот метод часто используется вместо [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) , если командлет не может работать с одним элементом за раз, как в случае с командлетом Sort.

Поскольку этот пример командлета Get-proc должен получать входные данные конвейера, он переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и использует реализации по умолчанию для [System. Management. Automation. командлета. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing). Переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) извлекает процессы и записывает их в командную строку с помощью метода [System. Management. Automation. командлета. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a>Вопросы, которые следует учитывать при обработке входных данных

- Источником по умолчанию для входных данных является явный объект (например, строка), предоставленный пользователем в командной строке. Дополнительные сведения см. в разделе [Создание командлета для обработки входных данных командной строки](./adding-parameters-that-process-command-line-input.md).

- Метод обработки входных данных также может принимать входные данные из выходного объекта вышестоящего командлета в конвейере. Дополнительные сведения см. в разделе [Создание командлета для обработки входных данных конвейера](./adding-parameters-that-process-pipeline-input.md). Имейте в виду, что командлет может получать входные данные из сочетания источников командной строки и конвейера.

- Нисходящий командлет может не возвращаться в течение длительного времени, а не вообще. По этой причине метод обработки ввода в командлете не должен удерживать блокировки во время вызовов [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), особенно блокировок, для которых область выходит за пределы экземпляра командлета.

> [!IMPORTANT]
> Командлеты никогда не должны вызывать [System. Console. WriteLine *](/dotnet/api/System.Console.WriteLine) или его эквивалент.

- Командлет может иметь переменные объекта для очистки после завершения обработки (например, если он открывает обработчик файла в методе [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и сохраняет открытый обработчик для использования [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)). Важно помнить, что среда выполнения Windows PowerShell не всегда вызывает метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , который должен выполнять очистку объектов.

Например, [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) может не вызываться, если в командлете отменено значение Мидуэй или если в какой-либо части командлета возникла неустранимая ошибка. Таким образом, командлет, требующий очистки объектов, должен реализовать полный шаблон [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения могла вызывать как [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , так и [System. IDisposable. Dispose *](/dotnet/api/System.IDisposable.Dispose) в конце обработки.

## <a name="code-sample"></a>Образец кода

Полный C# пример кода см. в разделе [GetProcessSample01 Sample](./getprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает сведения между командлетами с помощью объектов .NET. Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом. Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Тестирование командлета

Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке. Код для нашего примера командлета Get-proc небольшой, но он по-прежнему использует среду выполнения Windows PowerShell и существующий объект .NET, что достаточно для того, чтобы сделать его полезным. Давайте протестируем ее, чтобы лучше понять, что может сделать Get-proc и как можно использовать его выходные данные. Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

1. Запустите Windows PowerShell и получите текущие процессы, запущенные на компьютере.

    ```powershell
    get-proc
    ```

    Появится следующий вывод.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. Назначьте переменную для результатов командлета, чтобы упростить манипуляцию.

    ```powershell
    $p=get-proc
    ```

3. Возвращает количество процессов.

    ```powershell
    $p.length
    ```

    Появится следующий вывод.

    ```output
    63
    ```

4. Получение определенного процесса.

    ```powershell
    $p[6]
    ```

    Появится следующий вывод.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. Получение времени начала этого процесса.

    ```powershell
    $p[6].starttime
    ```

    Появится следующий вывод.

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. Получите процессы, для которых количество маркеров превышает 500, и отсортируйте результат.

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    Появится следующий вывод.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. Используйте командлет `Get-Member`, чтобы получить список свойств, доступных для каждого процесса.

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    Появится следующий вывод.

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a>См. также:

[Создание командлета для обработки входных данных командной строки](./adding-parameters-that-process-command-line-input.md)

[Создание командлета для обработки входных данных конвейера](./adding-parameters-that-process-pipeline-input.md)

[Создание командлета Windows PowerShell](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))

[Как работает Windows PowerShell](/previous-versions//ms714658(v=vs.85))

[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
