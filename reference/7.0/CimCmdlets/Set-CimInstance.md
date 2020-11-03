---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 9d68e59cf00e94a2318190800c47a4248a384e6f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229925"
---
# Set-CimInstance

## Краткий обзор
Изменяет экземпляр CIM на CIM-сервере, вызывая метод Модифинстанце класса CIM.

## SYNTAX

### Циминстанцекомпутерсет (по умолчанию)

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Циминстанцесессионсет

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### куерисессионсет

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### куерикомпутерсет

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Этот командлет изменяет экземпляр CIM на CIM-сервере.

Если параметр **InputObject** не указан, командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.
- Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .

Если указан параметр **InputObject** , командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.
- Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра **CimSession** , либо значение параметра **ComputerName** . Это не очень распространено.

## Примеры

### Пример 1. Задание экземпляра CIM

В этом примере для свойства **вариаблевалуе** задается значение **ABCD** с помощью параметра **запроса** . Можно изменить экземпляры, соответствующие запросу на языке запросов инструментарий управления Windows (WMI) (WQL).

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### Пример 2. Задание свойства экземпляра CIM с помощью конвейера

В этом примере извлекается объект экземпляра CIM, отфильтрованный по параметру **запроса** с помощью `Get-CimInstance` командлета. `Set-CimInstance`Командлет изменяет значение свойства **вариаблевалуе** на **ABCD**.

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### Пример 3. Установка свойства экземпляра CIM с помощью входного объекта

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

Этот пример извлекает объекты экземпляра CIM, отфильтрованные с помощью параметра запроса в, в переменную `$x` с помощью `Get-CimInstance` , а затем передает содержимое переменной в `Set-CimInstance` командлет. `Set-CimInstance` затем изменяет свойство **вариаблевалуе** на **someValue**. Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.

### Пример 4. Установка свойства экземпляра CIM

В этом примере извлекается объект экземпляра CIM, указанный в параметре **запроса** , в переменную `$x` с помощью `Get-CimInstance` командлета и изменяется значение свойства **вариаблевалуе** объекта для изменения. Затем объект экземпляра CIM сохраняется с помощью `Set-CimInstance` командлета.
Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### Пример 5. Отображение списка экземпляров CIM для изменения с помощью WhatIf

В этом примере используется общий параметр **WhatIf** для указания на то, что изменение не должно выполняться, но выводить только то, что было бы выполнено, если оно было выполнено.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### Пример 6. Задание экземпляра CIM после подтверждения от пользователя

В этом примере используется общий параметр **Confirm** , чтобы указать, что изменение должно выполняться только после подтверждения пользователя.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### Пример 7. Задание созданного экземпляра CIM

В этом примере создается экземпляр CIM с указанными свойствами с помощью `New-CimInstance` командлета и извлекается его содержимое в переменную `$x` . Переменная затем передается в `Set-CimInstance` командлет, который изменяет значение свойства **вариаблевалуе** на **someValue**.
Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## PARAMETERS

### -CimSession

Запускает командлеты на удаленном компьютере. Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором требуется выполнить операцию CIM. Можно указать полное доменное имя или NetBIOS-имя.

Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.

Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объект экземпляра CIM для использования в качестве входных данных.

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

### -Namespace

Указывает пространство имен для операции CIM. Пространством имен по умолчанию является root/cimv2. Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Оператионтимеаутсек

Указывает период времени, в течение которого командлет ожидает ответа от компьютера. По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.

Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.

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

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете. По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Задает свойства экземпляра CIM в виде хэш-таблицы (с использованием пар "имя-значение"). Изменяются только свойства, указанные с помощью этого параметра. Другие свойства экземпляра CIM не изменяются.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Указывает запрос, выполняемый на CIM-сервере для получения экземпляров CIM, на которых должен выполняться командлет. Диалект запроса можно указать с помощью параметра Куеридиалект.

Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ). Если указанное значение использует оператор WQL **Like** , необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Куеридиалект

Указывает язык запросов, используемый для параметра запроса. Допустимые значения для этого параметра: **WQL** или **CQL**. Значение по умолчанию — **WQL**.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса. URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.

ResourceURI можно использовать только с сеансами CIM, созданными с помощью протокола WSMan, или при указании параметра ComputerName, который создает сеанс CIM с помощью WSMan. Если указать этот параметр без указания параметра ComputerName или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр ResourceURI.

Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
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

### Microsoft.Management.Infrastructure.CimInstance

## Выходные данные

### Microsoft.Management.Infrastructure.CimInstance

Если указан параметр **PassThru** , этот командлет возвращает измененный объект экземпляра CIM.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimInstance](get-ciminstance.md)

[New-CimInstance](New-CimInstance.md)

[Remove-CimInstance](remove-ciminstance.md)
