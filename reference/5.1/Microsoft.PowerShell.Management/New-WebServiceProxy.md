---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227965"
---
# New-WebServiceProxy

## Краткий обзор
Создает объект прокси веб-службы, который позволяет использовать веб-службу и управлять ею в PowerShell.

## SYNTAX

### Неучетные данные (по умолчанию)

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### Учетные данные

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### уседефаулткредентиал

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## DESCRIPTION

`New-WebServiceProxy`Командлет позволяет использовать веб-службу в PowerShell. Командлет подключается к веб-службе и создает объект прокси веб-службы в PowerShell. Прокси-объект можно использовать для управления веб-службой.

Веб-служба — это программа на основе XML, которая обменивается данными по сети, особенно через Интернет. Платформа Microsoft .NET Framework включает прокси-объекты веб-служб, представляющие веб-службы в виде объектов .NET Framework.

## Примеры

### Пример 1. Создание учетной записи-посредника для веб-службы

В этом примере создается .NET Framework прокси веб-службы калькулятора в Windows PowerShell.

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### Пример 2. Создание прокси для веб-службы и указание пространства имен и класса

В этом примере `New-WebServiceProxy` командлет используется для создания .NET Framework прокси веб-службы калькулятора.

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

В команде используется параметр **URI** для указания универсального кода ресурса (URI), а также параметров **пространства имен** и **класса** для указания пространства имен и класса объекта.

### Пример 3. Отображение методов прокси веб-службы

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

В этом примере `Get-Member` командлет используется для вывода методов объекта прокси веб-службы в `$calc` переменной. Мы используем эти методы в следующем примере.

Обратите внимание, что имя **TypeName** объекта прокси, WebServiceProxy, отражает имена пространств имен и классов, которые были указаны в предыдущем примере.

### Пример 4. использование прокси веб-службы

```powershell
PS> $calc.Multiply(6,7)
42
```

В этом примере используется прокси веб-службы, хранящийся в `$calc` переменной. Команда использует метод **умножения** прокси-сервера.

## PARAMETERS

### -Class

Задает имя прокси-класса, который командлет создает для веб-службы. Значение этого параметра используется вместе с параметром **Namespace** , чтобы предоставить полное имя класса. Значение по умолчанию создается на основе универсального кода ресурса (URI).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь. Этот параметр служит альтернативой параметру **UseDefaultCredential** .

Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя этот командлет запрашивает пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Задает пространство имен для нового класса.

Значение этого параметра используется вместе со значением параметра **Class** для создания полного имени класса. Значение по умолчанию — **Microsoft. PowerShell. Commands. неввебсервицепрокси. аутоженератедтипес** плюс тип, созданный из универсального кода ресурса (URI).

Можно задать значение параметра **пространства имен** , чтобы можно было обращаться к нескольким веб-службам с одинаковыми именами.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — URI

Задает URI веб-службы. Введите URI или путь и имя файла, содержащего описание службы.

URI должен возвращать `.asmx` страницу или страницу, которая возвращает описание службы. Чтобы вернуть описание службы веб-службы, созданной с помощью ASP.NET, добавьте "? WSDL "по URL-адресу Web Service (например, `http://www.contoso.com/MyWebService.asmx?WSDL` ).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Уседефаулткредентиал

Указывает, что этот командлет использует учетные данные по умолчанию. Этот командлет задает для свойства **уседефаулткредентиал** в результирующем прокси-объекте значение true. Это альтернатива использованию параметра **Credential** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Объект прокси веб-службы

Этот командлет возвращает объект прокси веб-службы. Пространство имен и класс объекта определяются параметрами команды. Значение по умолчанию создается на основе входного универсального кода ресурса (URI).

## ПРИМЕЧАНИЯ

`New-WebServiceProxy` использует класс **System .NET. WebClient** для загрузки указанной веб-службы.

## Связанные ссылки

[New-Service](New-Service.md)
