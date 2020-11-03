---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/register-cimindicationevent?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-CimIndicationEvent
ms.openlocfilehash: a5e801c2b41fff618c78b4abcec9d90d09ea2323
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228225"
---
# Register-CimIndicationEvent

## Краткий обзор
Подписывается на события с помощью критерия фильтра или выражения запроса.

## SYNTAX

### Класснамекомпутерсет (по умолчанию)

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### класснамесессионсет

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### куерекспрессионсессионсет

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### куерекспрессионкомпутерсет

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Register-CimIndicationEvent`Командлет подписывается на события с помощью имени класса индикации или выражения запроса. Используйте параметр **SourceIdentifier** , чтобы присвоить имя подписке.

Этот командлет возвращает объект **подписки** . Этот объект можно использовать для отмены подписки.

## Примеры

### Пример 1. регистрация событий, созданных классом

Этот пример подписывается на события, создаваемые классом с именем **Win32_ProcessStartTrace** . Этот класс вызывает событие при запуске процесса.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
Get-Event -SourceIdentifier "ProcessStarted"
```

`Get-Event`Командлет получает события с подпиской **ProcessStarted** . Дополнительные сведения см. в разделе [Get-Event](../Microsoft.PowerShell.Utility/Get-Event.md).

> [!NOTE]
> В этом примере необходимо запустить PowerShell от имени администратора.

### Пример 2. регистрация событий с помощью запроса

В этом примере используется запрос для подписки на событие, формируемое при изменении экземпляра класса с именем **Win32_LocalTime** .

```powershell
$query = "SELECT * FROM CIM_InstModification WHERE TargetInstance ISA 'Win32_LocalTime'"
Register-CimIndicationEvent -Query $query -SourceIdentifier "Timer"
```

### Пример 3. Запуск скрипта при поступлении события

В этом примере показано, как использовать действие в ответ на событие. Переменная `$action` содержит блок скрипта для **действия** , который использует `$event` переменную для доступа к событию, полученному от CIM.

```powershell
$action = {
  $name = $event.SourceEventArgs.NewEvent.ProcessName
  $id = $event.SourceEventArgs.NewEvent.ProcessId
  Write-Host -Object "New Process Started : Name = $name
 ID = $id"
}
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

Дополнительные сведения см. в разделе [Win32_ProcessStartTrace](/previous-versions/windows/desktop/krnlprov/win32-processstarttrace).

### Пример 4. регистрация событий на удаленном компьютере

Этот пример подписывается на события на удаленном компьютере с именем **Server01** . События, полученные от CIM-сервера, хранятся в очереди событий в текущем сеансе PowerShell, а затем запускаются локально `Get-Event` для получения событий.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -ComputerName Server01
Get-Event -SourceIdentifier "ProcessStarted"
```

## PARAMETERS

### -Action

Указывает команды, обрабатывающие события. Команды, заданные этим параметром, выполняются при возникновении события вместо отправки события в очередь событий. Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.

Блок скрипта, указанный с помощью **действия** , может включать в себя `$Event` переменные,, `$EventSubscriber` `$Sender` , `$SourceEventArgs` и `$SourceArgs` автоматически, предоставляющие сведения о событии блоку сценария **действия** . Дополнительные сведения см. в разделе [об автоматических переменных](../microsoft.powershell.core/about/about_automatic_variables.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Выполняет команду с помощью указанного сеанса CIM. Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или. Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: ClassNameSessionSet, QueryExpressionSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassName

Указывает класс индикации, на который выполняется подписка. Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором требуется выполнить операцию CIM. Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.

При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan. Если этот параметр не указан, командлет выполняет операцию в локальной системе с помощью модели COM.

Если на одном компьютере выполняется несколько операций, подключайтесь с помощью сеанса CIM для повышения производительности.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QueryExpressionComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forward

Указывает, что события для подписки перенаправляются в сеанс на локальном компьютере. Этот параметр используется при регистрации событий, полученных на удаленном компьютере или в удаленном сеансе.

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

### -MaxTriggerCount

Параметр, указывающий, что подписчик должен быть автоматической отмены регистрации после запуска в указанное время. Если значение равно или меньше нуля, то количество случаев, когда событие может быть активировано без отмены регистрации, не ограничено.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

Указывает дополнительные данные, связываемые с этой подпиской на событие. Значение этого параметра отображается в свойстве **MessageData** всех событий, связанных с этой подпиской.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Указывает пространство имен для операции CIM. Пространством имен по умолчанию является **root/cimv2** . Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.

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

### -Query

Указывает запрос для выполнения на CIM-сервере. Если указанное значение содержит двойные кавычки `"` , одинарные кавычки `'` или обратную косую черту `\` , эти символы необходимо заключить в escape-символ обратной косой черты. Если указанное значение использует оператор WQL LIKE, то необходимо экранировать следующие символы, заключив их в квадратные скобки `[]` : процент `%` , символ подчеркивания `_` или открывающую квадратную скобку `[` .

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Куеридиалект

Указывает язык запросов, используемый для параметра **запроса** . Допустимые значения для этого параметра: **WQL** или **CQL** . Значение по умолчанию — **WQL** .

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Указывает имя подписки. Указанное имя должно быть уникальным в текущем сеансе. Значение по умолчанию — идентификатор GUID, который назначается PowerShell. Это значение отображается в значении свойства **SourceIdentifier** объекта подписчика и всех объектов событий, связанных с этой подпиской.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Указывает, что подписка на события скрыта. Этот параметр используется, если текущая подписка является частью более сложного механизма регистрации событий и не должна обнаруживаться независимым образом.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Этот командлет не принимает входные объекты.

## Выходные данные

### System.Object

Этот командлет выводит объект **подписки** .

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Event](../microsoft.powershell.utility/get-event.md)

[Remove-Event](../microsoft.powershell.utility/remove-event.md)

[Unregister-Event](../microsoft.powershell.utility/unregister-event.md)

[Write-Host](../microsoft.powershell.utility/write-host.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)
