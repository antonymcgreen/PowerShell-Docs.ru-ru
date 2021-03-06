---
ms.date: 09/13/2016
ms.topic: reference
title: Типы параметров командлета
description: Типы параметров командлета
ms.openlocfilehash: 8daaa3c778396e06a826de3b93e0610c51160fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660477"
---
# <a name="types-of-cmdlet-parameters"></a>Типы параметров командлета

В этом разделе описываются различные типы параметров, которые можно объявить в командлетах. Параметры командлета могут быть параметрами позиционированного, именованного, обязательного, необязательного или switch.

## <a name="positional-and-named-parameters"></a>Позиционированные и именованные параметры

Все параметры командлета являются либо именованными, либо параметрами позиционирования. Именованный параметр требует ввода имени параметра и аргумента при вызове командлета. Для позиционированного параметра требуется только ввод аргументов в относительном порядке. Затем система сопоставляет первый безымянный аргумент с первым позиционированным параметром. Система сопоставляет второй безымянный аргумент с вторым неименованным параметром и т. д. По умолчанию все параметры командлета являются именованными параметрами.

Чтобы определить именованный параметр, опустите `Position` ключевое слово в объявлении атрибута **Parameter** , как показано в следующем объявлении параметра.

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Чтобы определить параметр с указанием места, добавьте `Position` ключевое слово в объявление атрибута Parameter, а затем укажите расположение. В следующем примере `UserName` параметр объявляется как параметр с положением 0. Это означает, что первый аргумент вызова будет автоматически привязан к этому параметру.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> Хороший проект командлета рекомендует объявлять наиболее используемые параметры как параметры позиционирования, чтобы пользователь не вводил имя параметра при запуске командлета.

Позиционированные и именованные параметры принимают одиночные аргументы или несколько аргументов, разделенных запятыми. Несколько аргументов разрешены, только если параметр принимает коллекцию, например массив строк. В одном командлете можно смешивать позиционированные и именованные параметры. В этом случае система сначала извлекает именованные аргументы, а затем пытается сопоставлять остальные неименованные аргументы с заданными параметрами.

Следующие команды демонстрируют различные способы, с помощью которых можно указать один и несколько аргументов для параметров `Get-Command` командлета. Обратите внимание, что в двух последних примерах параметр **-Name** не нужно указывать, так как он `Name` определен как параметр с позиционированием.

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>Обязательные и необязательные параметры

Можно также определить параметры командлета как обязательные или необязательные параметры. (Обязательный параметр необходимо указать до того, как среда выполнения Windows PowerShell вызовет командлет.)  По умолчанию параметры определяются как необязательные.

Чтобы определить обязательный параметр, добавьте `Mandatory` ключевое слово в объявление атрибута Parameter и задайте для него значение `true` , как показано в следующем объявлении параметра.

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Чтобы определить необязательный параметр, опустите `Mandatory` ключевое слово в объявлении атрибута **Parameter** , как показано в следующем объявлении параметра.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>Параметры переключателя

Windows PowerShell предоставляет тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , который позволяет определить параметр, значение которого автоматически устанавливается в, `false` Если параметр не указан при вызове командлета. Везде, где это возможно, используйте параметры переключения вместо логических параметров.

Рассмотрим следующий пример. По умолчанию несколько командлетов Windows PowerShell не передают выходной объект в конвейер. Однако эти командлеты имеют `PassThru` параметр Switch, который переопределяет поведение по умолчанию. Если `PassThru` параметр указан при вызове этих командлетов, командлет возвращает выходной объект в конвейер.

Если требуется, чтобы параметр имел значение по умолчанию `true` , если параметр не указан в вызове, рассмотрите возможность отменять смысл параметра. Например, вместо присвоения атрибуту параметра логического значения `true` , объявите свойство как тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , а затем задайте для параметра значение по умолчанию `false` .

Чтобы определить параметр переключателя, объявите свойство как тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , как показано в следующем примере.

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

Чтобы командлет действовал для параметра, если он указан, используйте следующую структуру в одном из методов обработки ввода.

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
