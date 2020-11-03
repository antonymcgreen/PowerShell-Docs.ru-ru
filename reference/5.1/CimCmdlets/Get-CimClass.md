---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: e5700af4ff3f238d347e2c367416af08caf148ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226894"
---
# Get-CimClass

## Краткий обзор
Возвращает список классов CIM в определенном пространстве имен.

## SYNTAX

### Computering (по умолчанию)

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### Session, сеанс

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-CimClass`Командлет извлекает список классов CIM в определенном пространстве имен. Если имя класса не указано, командлет возвращает все классы в пространстве имен. В отличие от экземпляра CIM, классы CIM не содержат сеанса CIM или имени компьютера, откуда они извлекаются.

## Примеры

### Пример 1. получение всех определений классов

В этом примере возвращаются все определения классов в пространстве имен **root/cimv2**.

```powershell
Get-CimClass
```

### Пример 2. получение классов с указанным именем

Этот пример возвращает классы, содержащие слово **Disk** в своих именах.

```powershell
Get-CimClass -ClassName *disk*
```

### Пример 3. получение классов с использованием определенного имени метода

Этот пример получает классы, которые начинаются с имени **Win32** и имеют имя метода, которое начинается с **Term**.

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### Пример 4. получение классов с заданным именем свойства

Этот пример получает классы, которые начинаются с имени **Win32** и имеют свойство с именем **Handle**.

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### Пример 5. получение классов с заданным именем квалификатора

Этот пример получает классы, которые начинаются с имени **Win32** , содержат слово **Disk** в своих именах и имеют указанную **связь** квалификатора.

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### Пример 6. получение определений классов из определенного пространства имен

В этом примере возвращаются определения классов, содержащие слово **net** в своих именах из указанного **корня или standardCimv2** пространства имен.

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### Пример 7. получение определений классов с удаленного сервера

В этом примере возвращаются определения классов, содержащие слово **Disk** в своих именах из указанных удаленных серверов **Server01** и **Server02**.

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### Пример 8. получение классов с помощью сеанса CIM

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

Этот набор команд создает сеанс с несколькими компьютерами и сохраняет его в переменную `$s` с помощью `New-CimSession` командлета, а затем получает классы с помощью `Get-CimClass` командлета.

## PARAMETERS

### -CimSession

Запуск командлета в удаленном сеансе или на удаленном компьютере. Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или. Сеанс по умолчанию — текущий сеанс на локальном компьютере.

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

### -ClassName

Указывает имя класса CIM, для которого выполняется операция. Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ComputerName

Указывает компьютер, на котором требуется выполнить операцию CIM. Можно указать полное доменное имя (FQDN) или IP-адрес.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.

Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.

Если на одном компьютере выполняется несколько операций, использование сеанса CIM обеспечивает лучшую производительность.

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Имя_метода

Находит классы, имеющие метод, совпадающий с этим именем. С этим параметром можно использовать подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Namespace

Указывает пространство имен для операции CIM. Пространством имен по умолчанию является **root/cimv2**. Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### -PropertyName

Находит классы, имеющие свойство, соответствующее этому имени. С этим параметром можно использовать подстановочные знаки.

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

### -Куалифиернаме

Фильтрует классы по имени квалификатора уровня класса. С этим параметром можно использовать подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Этот командлет не принимает входные объекты.

## Выходные данные

### Microsoft. Management. Infrastructure. Цимкласс

Этот командлет возвращает объект класса CIM.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[New-CimSession](New-CimSession.md)
