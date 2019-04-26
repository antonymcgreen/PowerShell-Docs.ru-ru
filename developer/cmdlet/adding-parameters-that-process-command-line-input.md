---
title: Добавление параметров, которые обрабатывают данные в командной строке | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.assetid: da0b32f8-7b51-440e-a061-3177b5759e0e
caps.latest.revision: 9
ms.openlocfilehash: fb113086ce89e4becff9bcaf3232905fde2bf610
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068816"
---
# <a name="adding-parameters-that-process-command-line-input"></a>Добавление параметров для обработки входных данных команды

Один источник входных данных для командлета приведен пример командной строки. В этом разделе описывается добавление параметра **Get-Proc** командлет (который описан в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)), чтобы командлет может обрабатывать входные данные с локального компьютера, на основании явных объекты передаются в командлет. **Get-Proc** командлет описанные здесь извлекает процессы, на основе их имен и затем отображает сведения о процессах в командной строке.

В следующих разделах описаны в этом разделе:

- [Определение класса командлета](#Defining-the-Cmdlet-Class)

- [Объявление параметров](#Declaring-Parameters)

- [Поддержка проверки параметров](#Supporting-Parameter-Validation)

- [Переопределив метод обработки входных данных](#Overriding-an-Input-Processing-Method)

- [Пример кода](#Code-Sample)

- [Определение типов объектов и форматирование](#Defining-Object-Types-and-Formatting)

- [Создание командлета](#Building-the-Cmdlet)

- [Тестирование командлет](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a>Определение класса командлета

Первым этапом создания командлетов является названии командлета и объявление класса .NET Framework, который реализует командлет. Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get». (Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).

Вот объявление класса для **Get-Proc** командлета. Сведения об этом определении приведены в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a>Объявление параметров

Параметр командлета позволяет пользователю предоставлять командлету входные данные. В следующем примере **Get-Proc** и `Get-Member` являются именами конвейерных командлеты и `MemberType` является параметром для `Get-Member` командлета. Он имеет аргумент «свойство».

**PS> get-proc ; `get-member` -membertype property**

Чтобы объявить параметры командлета, необходимо сначала определить свойства, которые представляют параметры. В **Get-Proc** командлета, единственным параметром является `Name`, который в данном случае представляет имя объекта процесса .NET Framework для извлечения. Таким образом в классе командлета определяет свойство строкового типа, чтобы принять массив имен.

Ниже приведено объявление параметра для `Name` параметр **Get-Proc** командлета.

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

Сообщать среде выполнения Windows PowerShell, это свойство является `Name` параметра [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут добавляется к определению свойства. Базовый синтаксис для объявления этого атрибута `[Parameter()]`.

> [!NOTE]
> Параметр должен быть явно помечен как общедоступный. Параметры, которые не помечены как открытые, по умолчанию внутренний и не найдены средой выполнения Windows PowerShell.

Этот командлет использует массив строк для `Name` параметра. Если это возможно в командлет необходимо также определить параметры как массив, так как при этом командлет, чтобы принимать более одного элемента.

#### <a name="things-to-remember-about-parameter-definitions"></a>О чем следует помнить об определениях параметров

- Предопределенные Windows PowerShell параметров имена и типы данных следует повторно использовать настолько, насколько возможно обеспечить совместимость с помощью командлетов Windows PowerShell командлет. Например, если все командлеты используют предопределенный `Id` имя параметра для идентификации ресурса, пользователю придется легко понимать значение параметра, независимо от того, какой командлет, они используют. По сути параметр имена следуют тем же правилам, которые используются для имен переменных в общеязыковой среде выполнения (CLR). Дополнительные сведения об именах параметров см. в разделе [имена параметров командлета](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).

- Windows PowerShell зарезервировано несколько имен параметров для обеспечения согласованного пользовательского интерфейса. Не используйте эти имена параметров: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, и `OutBuffer`. Кроме того, зарезервированы следующие псевдонимы для этих имен параметров: `vb`, `db`, `ea`, `ev`, `ov`, и `ob`.

- `Name` — Это имя простых и распространенных параметров, рекомендуется использовать в командлеты. Лучше, можно выбрать любое имя параметра следующим образом, чем сложные имя, которое является уникальным для конкретного командлета и плохо запоминаются.

- Параметры не учитывается в Windows PowerShell, несмотря на то, что по умолчанию оболочка сохраняет регистр. Учет регистра в аргументы зависит от работы командлета. Аргументы передаются в параметр, как указано в командной строке.

- Примеры других объявлений параметров, см. в разделе [параметры командлета](./cmdlet-parameters.md).

## <a name="declaring-parameters-as-positional-or-named"></a>Объявление параметров как позиционные или именованные

Командлет необходимо задать каждый параметр как позиционные или именованные параметра. Оба вида параметров аргументов один, несколько аргументов, разделенных запятыми, логические параметры. Логический параметр, который также называется *переключения*, обрабатывает только логические параметры. Параметр используется для определения наличия параметра. Рекомендуемое значение по умолчанию — `false`.

Образец **Get-Proc** командлет определяет `Name` параметра в виде позиционным с позиции 0. Это означает, что для этого параметра автоматически вставляется первый аргумент, который пользователь вводит в командной строке. Если вы хотите определить именованный параметр, который пользователь должен указать имя параметра, из командной строки, оставьте `Position` ключевое слово из объявления атрибута.

> [!NOTE]
> Если параметры должны быть именованными, мы не рекомендуем, чтобы пользователям не придется ввести имя параметра сделать позиционные наиболее часто используемые параметры.

## <a name="declaring-parameters-as-mandatory-or-optional"></a>Объявление параметров как обязательные или необязательные

Командлет необходимо задать каждый параметр как необязательный или обязательный параметр. В образце **Get-Proc** командлета, `Name` параметр определен как необязательно, так как `Mandatory` ключевое слово не включен в объявление атрибута.

## <a name="supporting-parameter-validation"></a>Поддержка проверки параметров

Образец **Get-Proc** командлет добавляет атрибут проверки входных данных, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), `Name` параметр для включения проверки, входные данные не является ни `null` или пустым. Этот атрибут является одним из нескольких атрибутов проверки, предоставляемые Windows PowerShell. Примеры других атрибутов проверки, см. в разделе [проверка ввода параметра](./validating-parameter-input.md).

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a>Переопределив метод обработки входных данных

Если для обработки командной строки входных данных командлета, его необходимо переопределить соответствующие методы обработки ввода. Методы базовую обработку ввода, использованные в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).

**Get-Proc** командлета переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки `Name` входные параметры, предоставляемые пользователем или сценарий. Этот метод возвращает процессы для каждого имени запрошенного процесса или для всех процессов, если имя не указано. Обратите внимание, что в [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), вызов [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) выходные данные механизм для отправки выходных данных объекты в конвейер. Второй параметр этой вызов `enumerateCollection`, имеет значение `true` сообщать среде выполнения Windows PowerShell для перечисления выходной массив объектов процессов и один процесс записи за раз в командную строку.

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
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>Пример кода

Для полной C# пример кода, см. в разделе [пример GetProcessSample02](./getprocesssample02-sample.md).

## <a name="defining-object-types-and-formatting"></a>Определение типов объектов и форматирование

Windows PowerShell передает данные между командлетами, используя объекты .NET Framework. Следовательно командлет может потребоваться определить его собственного типа, или командлета может потребоваться расширить существующий тип предоставляемые другому командлету. Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).

## <a name="building-the-cmdlet"></a>Создание командлета

После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell с помощью оснастки Windows PowerShell. Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).

## <a name="testing-the-cmdlet"></a>Тестирование командлет

При регистрации командлета Windows PowerShell, его можно проверить, запустив его в командной строке. Ниже приведены два способа тестировать код для примера командлета. Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- В командной строке Windows PowerShell используйте следующую команду, чтобы получить список процесс Internet Explorer, который называется «IEXPLORE.»

    ```powershell
    PS> get-proc -name iexplore
    ```

Появляется следующий результат.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- Чтобы получить список процессов Internet Explorer, Outlook и Блокнот, с именем «IEXPLORE», «OUTLOOK» и «Блокнот», используйте следующую команду. При наличии нескольких процессов, то они отображаются.

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

Появляется следующий результат.

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a>См. также

[Добавление параметров конвейера обработки входных данных](./adding-parameters-that-process-pipeline-input.md)

[Создайте свой первый командлет](./creating-a-cmdlet-without-parameters.md)

[Расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[Регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Справочник по Windows PowerShell](../windows-powershell-reference.md)

[Примеры командлетов](./cmdlet-samples.md)
