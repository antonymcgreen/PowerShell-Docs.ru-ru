---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 49838449bd2ffe949c4b2f1310c3f68c40867908
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229802"
---
# Get-CimInstance

## Краткий обзор
Возвращает экземпляры CIM класса из CIM-сервера.

## SYNTAX

### Класснамекомпутерсет (по умолчанию)

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### ресаурцеурисессионсет

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### куерисессионсет

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### класснамесессионсет

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### Циминстанцесессионсет

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### Циминстанцекомпутерсет

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### ресаурцеурикомпутерсет

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### куерикомпутерсет

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## DESCRIPTION

`Get-CimInstance`Командлет возвращает экземпляры CIM класса из CIM-сервера. Для этого командлета можно указать либо имя класса, либо запрос. Этот командлет возвращает один или несколько объектов экземпляра CIM, представляющих моментальный снимок экземпляров CIM, имеющихся на CIM-сервере.

Если параметр **InputObject** не указан, командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.
- Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .

Если указан параметр **InputObject** , командлет работает одним из следующих способов:

- Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.
- Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра CimSession, либо значение параметра **ComputerName** .

## Примеры

### Пример 1. получение экземпляров CIM указанного класса

В этом примере извлекаются экземпляры CIM класса с именем **Win32_Process**.

```powershell
Get-CimInstance -ClassName Win32_Process
```

### Пример 2. Получение списка пространств имен с сервера WMI

В этом примере извлекается список пространств имен в **корневом** пространстве имен на сервере WMI.

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### Пример 3. получение экземпляров класса, отфильтрованных с помощью запроса

В этом примере извлекаются все экземпляры CIM, начинающиеся с буквы **P** класса с именем **Win32_Process** , с помощью запроса, указанного параметром **запроса** .

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### Пример 4. получение экземпляров класса, отфильтрованных с помощью имени класса и критерия фильтра

В этом примере извлекаются все экземпляры CIM, начинающиеся с буквы **P** класса с именем **Win32_Process** с помощью параметра Filter.

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### Пример 5. получение экземпляров CIM только с заполненными ключевыми свойствами

В этом примере создается новый экземпляр CIM в памяти для класса с именем **Win32_Process** со свойством ключа `@{ "Handle"=0 }` и сохраняется в переменной с именем `$x` . Переменная передается в командлет в качестве экземпляра CIM `Get-CimInstance` для получения конкретного экземпляра.

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### Пример 6. получение экземпляров CIM и их повторное использование

Этот пример получает экземпляры CIM класса с именем **Win32_Process** и сохраняет их в переменных `$x` и `$y` . Переменная `$x` затем форматируется в таблице, содержащей только свойства **Name** и **кернелмодетиме** , для которых задано **Автомасштабирование**.

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### Пример 7. получение экземпляров CIM с удаленного компьютера

В этом примере извлекаются экземпляры CIM класса с именем **Win32_ComputerSystem** с удаленных компьютеров с именами **Server01** и **Server02**.

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### Пример 8. получение только ключевых свойств, а не всех свойств

В этом примере извлекаются только ключевые свойства, которые уменьшают размер объекта и сетевого трафика.

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### Пример 9. получение только подмножества свойств, а не всех свойств

В этом примере извлекается только подмножество свойств, которое уменьшает размер объекта и сетевого трафика.

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

Экземпляр, полученный с помощью параметра **Property** , может использоваться для выполнения других операций CIM, например `Set-CimInstance` или `Invoke-CimMethod` .

### Пример 10. получение экземпляра CIM с помощью сеанса CIM

В этом примере создается сеанс CIM на компьютерах с именем **Server01** и **Server02** с помощью `New-CimSession` командлета, а сведения о сеансе сохраняются в переменной с именем `$s` . Затем содержимое переменной передается с `Get-CimInstance` помощью параметра **CimSession** , чтобы получить экземпляры CIM класса с именем **Win32_ComputerSystem**.

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## PARAMETERS

### -CimSession

Указывает сеанс CIM, который будет использоваться для этого командлета. Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или. Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Указывает имя класса CIM, для которого необходимо получить экземпляры CIM. Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.

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

### -ComputerName

Указывает компьютер, на котором требуется выполнить операцию CIM. Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес. Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.

Если на одном компьютере выполняется несколько операций, подключайтесь с помощью сеанса CIM для повышения производительности.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter

Указывает предложение WHERE для использования в качестве фильтра. Укажите предложение на языке запросов **WQL** или **CQL** . Не включайте `WHERE` ключевое слово в значение параметра.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Указывает объект экземпляра CIM для использования в качестве входных данных.

Если вы уже работаете с объектом экземпляра CIM, этот параметр можно использовать для передачи объекта экземпляра CIM для получения последнего моментального снимка с сервера CIM. При передаче объекта экземпляра CIM в качестве входных данных `Get-CimInstance` возвращает объект с сервера с помощью операции получения CIM вместо перечисления или операции запроса. Использование операции получения CIM более эффективно, чем получение всех экземпляров и последующее их фильтрация.

Если класс CIM не реализует операцию Get, то при указании параметра **InputObject** возвращается ошибка.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Кэйонли

Указывает, что возвращаются только объекты с заполненными ключевыми свойствами. Указание параметра **кэйонли** сокращает объем данных, передаваемых по сети.

Используйте параметр **кэйонли** , чтобы вернуть только небольшую часть объекта, которая может использоваться для других операций, таких как `Set-CimInstance` `Get-CimAssociatedInstance` командлеты или.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Указывает пространство имен класса CIM.

Пространством имен по умолчанию является **root/cimv2**. Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
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

### -Property

Задает набор свойств экземпляра для извлечения. Используйте этот параметр, если необходимо уменьшить размер возвращаемого объекта либо в памяти, либо по сети. Возвращаемый объект также содержит ключевые свойства, даже если они не перечислены с помощью параметра **Property** . Другие свойства класса существуют, но не заполнены.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Указывает запрос для выполнения на CIM-сервере. Если указанное значение содержит двойные кавычки `"` , одинарные кавычки `'` или обратную косую черту `\` , эти символы необходимо заключить в escape-символ обратной косой черты. Если указанное значение использует оператор WQL **Like** , то необходимо экранировать следующие символы, заключив их в квадратные скобки `[]` : процент `%` , символ подчеркивания `_` или открывающую квадратную скобку `[` .

Нельзя использовать запрос метаданных для получения списка классов или запроса события. Чтобы получить список классов, используйте `Get-CimClass` командлет. Чтобы получить запрос события, используйте `Register-CimIndicationEvent` командлет.

Диалект запроса можно указать с помощью параметра **куеридиалект** .

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

Указывает язык запросов, используемый для параметра запроса. Допустимые значения для этого параметра: **WQL** или **CQL**. Значение по умолчанию — **WQL**.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
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

**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan. Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .

Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Shallow

Указывает, что экземпляры класса возвращаются без включения экземпляров каких-либо дочерних классов. По умолчанию командлет возвращает экземпляры класса и его дочерних классов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
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

### Экземпляр CIM

Этот командлет принимает входные объекты, указанные с помощью параметра InputObject.

## Выходные данные

### Экземпляр CIM

Этот командлет возвращает один или несколько объектов экземпляра CIM, представляющих моментальный снимок экземпляров CIM на CIM-сервере.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Format-Table](../microsoft.powershell.utility/format-table.md)

[Get-CimAssociatedInstance](Get-CimAssociatedInstance.md)

[Get-CimClass](Get-CimClass.md)

[Invoke-CimMethod](invoke-cimmethod.md)

[New-CimInstance](New-CimInstance.md)

[Register-CimIndicationEvent](Register-CimIndicationEvent.md)

[Remove-CimInstance](remove-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)
