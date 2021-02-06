---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 1217e07d09213d7c0e223129207c085b9ba2d48d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603318"
---
# Invoke-CimMethod

## Краткий обзор
Вызывает метод класса CIM.

## SYNTAX

### Класснамекомпутерсет (по умолчанию)

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### класснамесессионсет

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ресаурцеурикомпутерсет

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Циминстанцесессионсет

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Циминстанцекомпутерсет

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ресаурцеурисессионсет

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Цимкласскомпутерсет

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Цимкласссессионсет

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### куерикомпутерсет

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### куерисессионсет

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-CimMethod`Командлет вызывает метод класса CIM или экземпляра CIM, используя пары "имя-значение", заданные параметром **arguments** .

Если параметр **InputObject** не указан, командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.
- Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .

Если указан параметр **InputObject** , командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.
- Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра **CimSession** , либо значение параметра **ComputerName** . Это не распространенный сценарий.

## Примеры

### Пример 1. вызов метода

В этом примере вызывается метод **Terminate** класса **Win32_Process** .

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### Пример 2. вызов метода с помощью объекта экземпляра CIM

Этот пример извлекает объект экземпляра CIM и сохраняет его в переменной с именем `$x` с помощью `Get-CimInstance` командлета. Содержимое переменной затем используется в качестве **InputObject** для `Invoke-CimMethod` командлета. Для **CimInstance** вызывается метод- **owner** .

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### Пример 3. вызов статического метода с помощью аргументов

В этом примере вызывается метод **CREATE** с именем, используя параметр **arguments** .

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### Пример 4. Проверка на стороне клиента

В этом примере выполняется проверка на стороне клиента для метода **XYZ** путем передачи объекта **Цимкласс** в `Invoke-CimMethod` .

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## PARAMETERS

### -Arguments

Задает параметры для передачи в вызываемый метод. Укажите значения для этого параметра в виде пар "имя-значение", хранящихся в хэш-таблице. Порядок введенных значений не важен.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Цимкласс

Указывает объект класса CIM, представляющий определение класса CIM на сервере. Используйте этот параметр при вызове статического метода класса.

С помощью `Get-CimClass` командлета можно получить определение класса с сервера.

Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession

Выполняет команду с помощью указанного сеанса CIM. Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или. Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Указывает имя класса CIM, для которого выполняется операция. Этот параметр используется только для статических методов. Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором требуется выполнить операцию CIM. Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.

При использовании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan. В противном случае командлет выполняет операцию на локальном компьютере с помощью модели COM.

Подключение с помощью сеанса CIM для повышения производительности при выполнении нескольких операций на одном компьютере.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Указывает объект экземпляра CIM, используемый в качестве входных данных для вызова метода. Этот параметр может использоваться только для вызова методов экземпляра. Чтобы вызвать статические методы класса, используйте параметр **класса** или параметр **Цимкласс** .

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Имя_метода

Указывает имя вызываемого метода CIM. Этот параметр является обязательным и не может быть NULL или пустым. Чтобы вызвать статический метод класса CIM, используйте параметр **className** или **Цимкласс** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Указывает пространство имен для операции CIM. Пространством имен по умолчанию является **root/cimv2**. Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Оператионтимеаутсек

Указывает период времени, в течение которого командлет ожидает ответа от компьютера. По умолчанию значение равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.

Если параметр **оператионтимеаутсек** имеет значение, меньшее, чем время ожидания попытки подключения по умолчанию (3 минуты), сетевые сбои, которые больше, чем значение параметра **оператионтимеаутсек** , не могут быть восстановлены.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Указывает запрос для выполнения на CIM-сервере. Метод вызывается для экземпляров, полученных в результате запроса. Диалект запроса можно указать с помощью параметра **куеридиалект** .

Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ). Если указанное значение использует оператор WQL LIKE, необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Куеридиалект

Указывает язык запросов, используемый для параметра запроса. Допустимые значения для этого параметра: **WQL** или **CQL**.

Значение по умолчанию — **WQL**.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.
URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.

**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.

При указании этого параметра без указания параметра **ComputerName** или при указании сеанса CIM, созданного с помощью протокола DCOM, возникает ошибка. Протокол DCOM не поддерживает параметр **resourceUri** .

Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Класс CIM

Этот командлет принимает класс CIM в качестве входного объекта.

### Экземпляр CIM

Этот командлет принимает экземпляр CIM в качестве входного объекта.

## Выходные данные

### System. Management. Automation. PSCustomObject

Этот командлет возвращает объект.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)

