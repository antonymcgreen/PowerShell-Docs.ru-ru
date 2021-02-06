---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d81117ad6885d660e31f031bd8134096db91b7da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601478"
---
# New-CimInstance

## Краткий обзор
Создает экземпляр CIM.

## SYNTAX

### Класснамекомпутерсет (по умолчанию)

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### класснамесессионсет

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ресаурцеурисессионсет

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ресаурцеурикомпутерсет

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Цимкласссессионсет

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Цимкласскомпутерсет

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`New-CimInstance`Командлет создает экземпляр класса CIM на основе определения класса либо на локальном компьютере, либо на удаленном компьютере. По умолчанию `New-CimInstance` командлет создает экземпляр на локальном компьютере.

## Примеры

### Пример 1. Создание экземпляра класса CIM

В этом примере создается экземпляр класса CIM с именем win32_environment в пространстве имен root/cimv2 на компьютере.

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

Проверка на стороне клиента не выполняется, если класс не существует, свойства неверны или сервер отклоняет вызов. Если экземпляр создан успешно, командлет выводит только что созданный экземпляр.

### Пример 2. Создание экземпляра класса CIM с помощью схемы класса

В этом примере извлекается объект класса CIM и сохраняется в переменной с именем `$class` . После этого содержимое переменной передается в `New-CimInstance` командлет.

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### Пример 3. Создание динамического экземпляра на клиенте

В этом примере создается динамический экземпляр класса CIM с именем **Win32_Process** на клиентском компьютере без получения экземпляра с сервера. Новый экземпляр хранится в переменной `$a` . Этот динамический экземпляр можно использовать для выполнения операций, если экземпляр с этим ключом существует на сервере.

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

`Get-CimInstance`Затем командлет извлекает определенный единственный экземпляр. `Invoke-CimMethod`Командлет вызывает метод метода  with для полученного экземпляра.

### Пример 4. Создание экземпляра для класса CIM определенного пространства имен

В этом примере получается экземпляр класса CIM с именем **MSFT_Something** в пространстве имен **root/где** и сохраняется в переменной с именем `$class` . Переменная передается в `New-CimInstance` командлет для создания нового экземпляра CIM и выполнения проверки на стороне клиента в новом экземпляре.

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

В этом примере использование параметра **Цимкласс** вместо параметра **className** подтверждает, что **Prop1** и **Prop2** фактически существуют и что ключи помечены правильно.

Параметр **ComputerName** или **CimSession** нельзя использовать с параметром **клиентонли** .

## PARAMETERS

### -Цимкласс

Указывает объект класса CIM, представляющий тип экземпляра. Используйте `Get-CimClass` командлет, чтобы получить объявление класса с компьютера. Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
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
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Указывает имя класса CIM, в котором операция создает экземпляр. Примечание. для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Клиентонли

Указывает, что экземпляр создается только в PowerShell без перехода на CIM-сервер. Этот параметр можно использовать для создания экземпляра CIM в памяти, который будет использоваться в последующих операциях PowerShell.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором требуется выполнить операцию CIM. Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WSMan.

Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.

Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key

Задает свойства, используемые в качестве ключей. **CimSession** и **ComputerName** нельзя использовать, если указан **ключ** .

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Задает пространство имен класса для нового экземпляра. Пространством имен по умолчанию является **root/cimv2**.
Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Оператионтимеаутсек

Указывает период времени, в течение которого командлет ожидает ответа от сервера CIM. По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера. Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.

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

### -Property

Задает свойства экземпляра CIM, используя хэш-таблицу (пары "имя-значение").

Если указан параметр **Цимкласс** , `New-CimInstance` командлет выполняет проверку свойства на клиенте, чтобы убедиться, что указанные свойства соответствуют объявлению класса на сервере. Если параметр **Цимкласс** не указан, проверка свойства выполняется на сервере.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса. URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.

**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan. Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .

Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
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

### None

Этот командлет не принимает входные объекты.

## Выходные данные

### System.Object

Этот командлет возвращает объект, содержащий сведения об экземпляре CIM.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)

[Remove-CimInstance](remove-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)

