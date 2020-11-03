---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: d986ba683c091cb8652b077f7f915f399a556002
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229934"
---
# Get-CimAssociatedInstance

## Краткий обзор
Извлекает экземпляры CIM, которые подключены к определенному экземпляру CIM с помощью ассоциации.

## SYNTAX

### Computering (по умолчанию)

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### Session, сеанс

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## DESCRIPTION

`Get-CimAssociatedInstance`Командлет извлекает экземпляры CIM, подключенные к определенному экземпляру CIM, который называется экземпляром источника, по ассоциации.

В ассоциации каждый экземпляр CIM имеет именованную роль и один и тот же экземпляр CIM может участвовать в ассоциации в разных ролях.

Если параметр InputObject не указан, командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.
- Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .

## Примеры

### Пример 1. получение всех связанных экземпляров конкретного экземпляра

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

Этот набор команд извлекает экземпляры класса с именем Win32_LogicalDisk и сохраняет данные в переменной `$disk` с именем с помощью `Get-CimInstance` командлета. Первый экземпляр логического диска в переменной затем используется в качестве входного объекта для `Get-CimAssociatedInstance` командлета, чтобы получить все связанные экземпляры CIM указанного экземпляра CIM.

### Пример 2. получение всех связанных экземпляров определенного типа

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

Этот набор команд извлекает все экземпляры класса **Win32_LogicalDisk** и сохраняет их в переменной с именем `$disk` . Первый экземпляр логического диска в переменной затем используется в качестве входного объекта для `Get-CimAssociatedInstance` командлета, чтобы получить все связанные экземпляры, связанные с помощью указанного класса ассоциации **Win32_DiskPartition** .

### Пример 3. получение всех связанных экземпляров с помощью квалификатора определенного класса

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

Этот набор команд извлекает службы, которые зависят от службы WMI, и сохраняет их в переменной с именем `$s` . Имя класса ассоциации для **Win32_DependentService** извлекается с помощью `Get-CimClass` командлета путем указания **ассоциации** в качестве квалификатора, а затем передается с помощью $s `Get-CimAssociatedInstance` командлету для получения всех связанных экземпляров полученного класса Association.

## PARAMETERS

### -Ассоциация

Указывает имя класса ассоциации. Если этот параметр не указан, командлет возвращает все существующие объекты связи любого типа.

Например, если класс A связан с классом B через две ассоциации, AB1 и AB2, то этот параметр можно использовать для указания типа ассоциации: AB1 или AB2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession

Выполняет команду с помощью указанного сеанса CIM. Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` или `Get-CimSession` . Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором требуется выполнить операцию CIM. Можно указать полное доменное имя или NetBIOS-имя.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.

Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.

Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает входные данные для этого командлета. Можно использовать данный параметр или передавать входные данные в этот командлет.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Кэйонли

Возвращает объекты только с заполненными ключевыми свойствами. Это сокращает объем данных, передаваемых по сети.

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

### -Namespace

Указывает пространство имен для операции CIM. Пространством имен по умолчанию является root/cimv2.

> [!NOTE]
> Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: (All)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса. URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.

**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan. Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникает ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .

Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ресулткласснаме

Указывает имя класса для связанных экземпляров. Экземпляр CIM может быть связан с одним или несколькими экземплярами CIM. Если не указать имя результирующего класса, возвращаются все связанные экземпляры CIM.

По умолчанию значение этого параметра равно null, и возвращаются все связанные экземпляры CIM.

Результаты ассоциации можно отфильтровать в соответствии с именем определенного класса. Фильтрация происходит на сервере. Если этот параметр не указан, `Get-CIMAssociatedInstance` возвращает все существующие связи. Например, если класс A связан с классами B, C и D, то этот параметр можно использовать для ограничения выходных данных определенным типом (B, C или D).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

Этот командлет не принимает входные объекты.

## Выходные данные

### System.Object

Этот командлет возвращает объект.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)
