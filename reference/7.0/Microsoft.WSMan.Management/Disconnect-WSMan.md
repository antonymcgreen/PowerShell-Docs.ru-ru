---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: a754b6530ecd8b3153d82327a246cbb387d53dd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226081"
---
# Disconnect-WSMan

## Краткий обзор
Отключает клиента от службы удаленного управления Windows на удаленном компьютере.

## SYNTAX

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disconnect-WSMan** отключает клиента от службы WinRM на удаленном компьютере.
Если сеанс WS-Management сохранен в переменной, объект сеанса остается в переменной, но состояние сеанса WS-Management закрывается.
Этот командлет можно использовать в контексте поставщика WSMan для отключения клиента от службы удаленного управления Windows на удаленном компьютере.
Однако его также можно использовать для отключения от службы удаленного управления Windows на удаленных компьютерах перед изменением поставщика WSMan.

Дополнительные сведения о способах подключения к службе удаленного управления Windows на удаленном компьютере см. в описании Connect-WSMan.

## Примеры

### Пример 1. Удаление подключения к удаленному компьютеру

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

Эта команда удаляет подключение к удаленному компьютеру с именем Server01.

Этот командлет обычно используется в контексте WSMan поставщика для отключения от удаленного компьютера, в данном случае это компьютер server01.
Однако можно также использовать **Disconnect-WSMan** для удаления соединений с удаленными компьютерами перед изменением поставщика WSMan.
Эти подключения не отображаются в списке ComputerName.

## PARAMETERS

### -ComputerName
Задает имя компьютера, для которого требуется выполнить операцию управления.
Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.
Для указания локального компьютера используйте его имя, localhost или точку (.).
Локальный компьютер используется по умолчанию.
Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.
Можно передать значение этого параметра в командлет.

Отключиться от локального узла нельзя.
Это значит, что невозможно отключить подключение по умолчанию к локальному компьютеру.
Однако при создании отдельного соединения с локальным компьютером, например с помощью имени компьютера.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
