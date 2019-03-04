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
ms.openlocfilehash: 75a45e539b45b50714951f2b992d9ecf69de4664
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860650"
---
# <a name="creating-a-cmdlet-without-parameters"></a>Создание командлета без параметров

В этом разделе описывается, как создать командлет, который извлекает данные из локального компьютера без использования параметров, а затем записывает данные в конвейер. Командлет, описанные здесь является командлет Get-Proc, который извлекает сведения о процессах на локальном компьютере, а затем отображает эти сведения в командной строке.

Следующие подразделы этого раздела.

- [Именование командлет](#Naming-the-Cmdlet)

- [Определение класса командлета](#Defining-the-Cmdlet-Class)

- [Переопределив метод обработки входных данных](#Overriding-an-Input-Processing-Method)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование](#Defining-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

> [!NOTE]
> Имейте в виду, что при написании командлетов, Windows PowerShell® ссылочные сборки загружаются на диск (по умолчанию в C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0). Они не установлены в глобальный кэш сборок (GAC).

## <a name="naming-the-cmdlet"></a>Именование командлет

Имя командлета состоит из команды, которая указывает, что принимает действие командлета и существительное, который указывает элементы, которые обрабатывают командлет. Так как этот командлет Get-Proc пример извлекает объекты процессов, используется команда «Get», определяемый [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) перечисления и термин «Proc», чтобы указать, что командлет работает с элементами процесса.

При именовании командлетов, не используйте следующие символы: #, () {} [] & - / \ $;: "" <> &#124; ? @ ` .

### <a name="choosing-a-noun"></a>Выбор существительное

Следует выбрать существительное, характерное. Лучше всего использовать существительное единственном числе, префикс сокращенную версию имя продукта. Пример командлета этот тип называется "`Get-SQLServer`«.

### <a name="choosing-a-verb"></a>Выбор команды

Следует использовать команды из списка утвержденных командлет имен команд. Дополнительные сведения о утвержденных командлета, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

## <a name="defining-the-cmdlet-class"></a>Определение класса командлета

После выбора имени командлета, определите класс .NET для реализации командлет. Вот определение класса для этого командлета Get-Proc образца:

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

Обратите внимание, что перед определением класса [System.Management.Automation.Cmdletattribute](/dotnet/api/System.Management.Automation.CmdletAttribute) атрибут, с помощью синтаксиса `[Cmdlet(verb, noun, ...)]`, используемое для идентификации этого класса, как командлет. Это единственный обязательный атрибут для всех командлетов, и он позволяет среде выполнения Windows PowerShell для корректного вызова. Можно задать атрибут ключевые слова для дальнейшего объявления класса, при необходимости. Имейте в виду, что объявление атрибута для нашего примера GetProcCommand класса объявляются только имя существительное и команда имена для командлета Get-Proc.

> [!NOTE]
> Для всех классов атрибутов Windows PowerShell ключевые слова, которые можно задать соответствуют свойствам класса атрибута.

При присвоении имени класса командлета, рекомендуется в соответствии с именем командлета в имени класса. Чтобы сделать это, используйте форму «VerbNounCommand» и замените глагол и существительное, используемый в имени командлета «Глагол» и «Существительное». Как показано в предыдущем определение класса, командлет Get-Proc примере определяется класс с именем GetProcCommand, который является производным от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) базового класса.

> [!IMPORTANT]
> Если вы хотите определить командлет, который напрямую обращается к среде выполнения Windows PowerShell, класс .NET должен быть производным от [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса. Дополнительные сведения об этом классе см. в разделе [Создание командлета, определяет параметр наборов](./adding-parameter-sets-to-a-cmdlet.md).

> [!NOTE]
> Класс для командлета должны быть помечены как открытые. Классы, которые не помечены как открытые по умолчанию к внутренним и не будет найдена средой выполнения Windows PowerShell.

Windows PowerShell использует [Microsoft.Powershell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) пространство имен для классов его командлет. Рекомендуется поместить командлет классы в пространстве имен команд API пространства имен, например, xxx.PS.Commands.

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класс предоставляет три метода основной обработки ввода, по крайней мере один из которых необходимо переопределить командлета. Дополнительные сведения об обработке записей с помощью Windows PowerShell см. в разделе [как Windows PowerShell работает](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).

Для всех типов входных данных среда выполнения Windows PowerShell вызывает [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) , чтобы включить обработку. Если в командлете необходимо выполнить предварительную обработку или установки, его можно сделать путем переопределения этого метода.

> [!NOTE]
> Windows PowerShell используется термин «запись» для описания набора значений параметров, при выполнении командлета указано.

Если командлет принимает входные данные конвейера, необходимо переопределить [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод и при необходимости [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)метод. Например, командлет может переопределить оба метода, если он собирает все входные данные с помощью [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и затем обрабатывает входные данные как единое целое, а не одного элемента за раз, как `Sort-Object` командлет не.

Если командлет не принимает входные данные конвейера, следует переопределить [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод. Имейте в виду, что этот метод часто используется вместо [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) когда командлет не может работать с одного элемента за раз, как в случае для сортировки командлета.

Так как этот пример командлета Get-Proc должен получить входные данные конвейера, он переопределяет [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метода и использует реализации по умолчанию для [ System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing). [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределения извлекает процессы и записывает их в командной строке с помощью [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод.

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

#### <a name="things-to-remember-about-input-processing"></a>О чем следует помнить о обработки ввода

- Источник по умолчанию для входных данных — явные объект (например, строка), указанное пользователем в командной строке. Дополнительные сведения см. в разделе [Создание командлету входные данные командной строки процесс](./adding-parameters-that-process-command-line-input.md).

- Метод обработки входных данных можно также вводить данные из объекта выходных данных вышестоящего командлета в конвейере. Дополнительные сведения см. в разделе [Создание командлету входные данные конвейера процесс](./adding-parameters-that-process-pipeline-input.md). Имейте в виду, что командлета можно получать входные данные на основе сочетания командной строки и конвейера источников.

- Командлет подчиненных могут не возвращать в течение длительного времени или вообще не. По этой причине метод командлета обработки входных данных не следует удерживать блокировки во время вызовов [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), особенно блокировок, для которых область расширяется за пределы экземпляра командлет.

> [!IMPORTANT]
> Никогда не должен вызывать командлеты [System.Console.Writeline*](/dotnet/api/System.Console.WriteLine) или его эквивалент.

- Командлет может быть объектные переменные для очистки после завершения обработки (например, в том случае, если он открывает дескриптор файла в [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод и сохраняет дескриптор откройте для использования, [ System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)). Важно помнить, что среда выполнения Windows PowerShell не всегда вызывает [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод, который следует выполнить очистку объекта.

Например [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) не может вызываться, если командлет отменяется в середине или если завершающей в любой части командлета возникает ошибка. Таким образом, следует реализовать полный командлет, который требует очистки объектов [System.Idisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, чтобы среда выполнения может вызвать оба [ System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) и [System.Idisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose) в конце обработки.

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример GetProcessSample01](./getprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает данные между командлетами, используя объекты .NET. Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке. Код для командлета Get-Proc наш пример невелика, но по-прежнему использует среда выполнения Windows PowerShell и существующий объект .NET, который достаточно, чтобы сделать его полезным. Давайте протестируем его, чтобы лучше понять возможности Get-Proc и использования его выходные данные. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

1. Запустите Windows PowerShell и получение текущих процессов, запущенных на компьютере.

    ```powershell
    get-proc
    ```

    Появляется следующий результат.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. Присвоить переменной результаты для простоты управления.

    ```powershell
    $p=get-proc
    ```

3. Получите число процессов.

    ```powershell
    $p.length
    ```

    Появляется следующий результат.

    ```output
    63
    ```

4. Получение определенного процесса.

    ```powershell
    $p[6]
    ```

    Появляется следующий результат.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. Получите время начала этого процесса.

    ```powershell
    $p[6].starttime
    ```

    Появляется следующий результат.

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. Возвращает процессы, для которых значение счетчика дескрипторов больше 500 и отсортировать результаты.

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    Появляется следующий результат.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. Используйте `Get-Member` командлет, чтобы получить список свойств, доступных для каждого процесса.

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    Появляется следующий результат.

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a>См. также

[Создание командлета для обработки входных данных командной строки](./adding-parameters-that-process-command-line-input.md)

[Создание командлета для обработки входных данных конвейера](./adding-parameters-that-process-pipeline-input.md)

[Как создать командлет Windows PowerShell](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[Расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Как работает Windows PowerShell](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)