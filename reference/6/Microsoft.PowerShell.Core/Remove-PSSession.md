---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: a6b980b022672fbc84549987e1cb5673f51e3dc4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229253"
---
# Remove-PSSession

## Краткий обзор
Закрывает один или несколько сеансов PowerShell (PSSession).

## SYNTAX

### Id (по умолчанию)

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Сеанс

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerId

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMId

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### name

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ИмяКомпьютера

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Remove-PSSession** Закрывает сеансы PowerShell ( **PSSession** ) в текущем сеансе.
Он останавливает все команды, запущенные в **PSSession** , завершает **сеанс PSSession** и освобождает ресурсы, которые использовались в **PSSession** .
Если **сеанс PSSession** подключен к удаленному компьютеру, этот командлет также закрывает подключение между локальным и удаленным компьютерами.

Чтобы удалить **PSSession** , введите *имя* , *ComputerName* , *идентификатор* или *InstanceId* сеанса.

Если *сеанс PSSession* сохранен в переменной, то объект сеанса остается в переменной, но состояние *PSSession* закрыто.

## Примеры

### Пример 1. Удаление сеансов с помощью идентификаторов

```powershell
Remove-PSSession -Id 1, 2
```

Эта команда удаляет **PSSession** с идентификаторами 1 и 2.

### Пример 2. Удаление всех сеансов в текущем сеансе

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

Эти команды удаляют все **PSSession** в текущем сеансе.
Хотя три формата команд отличаются, они действуют одинаково.

### Пример 3. закрытие сеансов с помощью имен

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

Эти команды закрывают **PSSession** , подключенные к компьютерам, имена которых начинаются с серв.

### Пример 4. закрытие сеансов, подключенных к порту

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

Эта команда закрывает **PSSession** , подключенные к порту 90.
Этот формат команды можно использовать для идентификации **PSSession** по свойствам, отличным от *ComputerName* , *Name* , *InstanceId* и *ID*.

### Пример 5. Закрытие сеанса на основе идентификатора экземпляра

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

Эти команды показывают, как закрыть **сеанс PSSession** на основе идентификатора экземпляра или **ремотерунспацеид**.

Первая команда использует командлет **Get-PSSession** для получения **PSSession** в текущем сеансе.
Он использует оператор конвейера (|) для отправки **PSSession** в командлет Format-Table, который форматирует свойства **ComputerName** и **InstanceId** в таблице.
Параметр *AutoSize* сжимает столбцы для вывода.

На полученном экране можно указать, что **сеанс PSSession** должен быть закрыт, а затем скопировать и вставить *InstanceId* этого **сеанса PSSession** во вторую команду.

Вторая команда использует командлет **Remove-PSSession** для удаления *сеанса PSSession* с указанным идентификатором экземпляра.

### Пример 6. Создание функции, которая удаляет все сеансы в текущем сеансе

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

Эта функция удаляет все **PSSession** в текущем сеансе.
После добавления этой функции в профиль PowerShell для удаления всех сеансов введите `EndPSS` .

## PARAMETERS

### -ComputerName

Указывает массив имен компьютеров.
Этот командлет закрывает **PSSession** , подключенные к указанным компьютерам.
Можно использовать подстановочные знаки.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ContainerId

Указывает массив идентификаторов контейнеров. Этот командлет удаляет сеансы для каждого из указанных контейнеров. Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров. Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id

Указывает массив идентификаторов сеансов.
Этот командлет закрывает *PSSession* с указанными идентификаторами.
Введите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range (..), чтобы указать диапазон идентификаторов.

Идентификатор — это целое число, уникально идентифицирующее **сеанс PSSession** в текущем сеансе.
Проще запомнить и ввести, чем *InstanceId* , но он уникален только в текущем сеансе.
Чтобы найти идентификатор **сеанса PSSession** , выполните командлет Get-PSSession без параметров.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает массив идентификаторов экземпляров.
Этот командлет закрывает **PSSession** с указанными идентификаторами экземпляров.

Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** в текущем сеансе.
Идентификатор экземпляра уникален, даже если на одном компьютере выполняется несколько сеансов.

Идентификатор экземпляра хранится в свойстве **InstanceId** объекта, представляющего **сеанс PSSession**.
Чтобы найти **InstanceId** **PSSession** в текущем сеансе, введите `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает массив понятных имен сеансов.
Этот командлет закрывает **PSSession** с указанными понятными именами.
Можно использовать подстановочные знаки.

Поскольку понятное имя **PSSession** может не быть уникальным, при использовании параметра *Name* рекомендуется также использовать параметр *WhatIf* или *Confirm* в команде **Remove-PSSession** .

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Session

Указывает объекты сеанса **PSSession** , которые нужно закрыть.
Введите переменную, которая содержит **PSSession** , или команду, которая создает или получает **pssession** , например New-PSSession или **Get-PSSession** .
Можно также передать один или несколько объектов сеанса в командлет **Remove-PSSession**.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### — VMId

Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.
Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.
Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Указывает массив имен виртуальных машин.
Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.
Чтобы просмотреть доступные виртуальные машины, используйте командлет **Get-VM** .

```yaml
Type: System.String[]
Parameter Sets: VMName
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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.Runspaces.PSSession

Объект сеанса можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет

Этот командлет не создает никаких объектов.

## ПРИМЕЧАНИЯ

* Параметр *ID* является обязательным. Чтобы удалить все **PSSession** в текущем сеансе, введите `Get-PSSession | Remove-PSSession` .
* **Сеанс PSSession** использует постоянное подключение к удаленному компьютеру. Создайте **сеанс PSSession** для выполнения ряда команд, которые совместно используют данные. Для получения дополнительных сведений введите `Get-Help about_PSSessions`.
* **PSSession** относятся к текущему сеансу. После завершения сеанса **PSSession** , созданный в этом сеансе, принудительно закрывается.

## Связанные ссылки

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
