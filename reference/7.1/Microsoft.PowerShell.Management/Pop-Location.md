---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: c2a9af56c395409fd08c3126d36126a171ff7ec7
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "93230242"
---
# Pop-Location

## Краткий обзор
Меняет текущее расположение на расположение, указанное в последней записи стека.

## SYNTAX

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

`Pop-Location`Командлет изменяет текущее расположение на расположение, которое недавно было отправлено в стек с помощью `Push-Location` командлета. Можно открыть расположение из стека по умолчанию или из стека, созданного с помощью `Push-Location` команды.

## Примеры

### Пример 1. Переход к последнему расположению

```
PS C:\> Pop-Location
```

Эта команда меняет текущее расположение на расположение, указанное в последней записи текущего стека.

### Пример 2. Переход к последнему расположению в именованном стеке

```
PS C:\> Pop-Location -StackName "Stack2"
```

Эта команда меняет текущее расположение на расположение, указанное в последней записи стека Stack2.

Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

### Пример 3. Перемещение между расположениями для разных поставщиков

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

Эти команды используют `Push-Location` `Pop-Location` командлеты и для перемещения между расположениями, поддерживаемыми различными поставщиками PowerShell. Команды используют `pushd` псевдоним для `Push-Location` и `popd` псевдоним для `Pop-Location` .

Первая команда помещает текущее расположение файловой системы в стек и переходит на диск HKLM, поддерживаемый поставщиком реестра PowerShell.

Вторая команда помещает расположение реестра в стек и переходит в расположение, поддерживаемое поставщиком сертификатов PowerShell.

Две последние команды извлекают эти расположения из стека. Первая `popd` команда возвращается к диску реестра, а вторая команда возвращается к диску файловой системы.

## PARAMETERS

### -PassThru

Передает объект, представляющий расположение в конвейер. По умолчанию этот командлет не создает выходные данные.

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

### -StackName

Указывает стек папок, из которого будет взято расположение. Введите имя стека папок.

Без этого параметра `Pop-Location` извлекает расположение из текущего стека расположения. По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell. Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета. Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

`Pop-Location` невозможно открыть расположение из неименованного стека по умолчанию, если он не является текущим стеком расположения.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет, System. Management. Automation. PathInfo

Этот командлет создает объект **System. Management. Automation. PathInfo** , представляющий расположение, если указан параметр **PassThru** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

PowerShell поддерживает несколько пространств выполнения для каждого процесса. Каждое пространство выполнения имеет свой собственный _текущий каталог_ .
Это не то же самое, что `[System.Environment]::CurrentDirectory` . Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.

Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время. Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.

Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам. Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке. PowerShell позволяет хранить расположения поставщиков в стеках расположений.

PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения. Если имя стека не указано, PowerShell использует текущий стек расположения. По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.

Для управления стеками расположений используйте `*-Location` командлеты PowerShell следующим образом:

- Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.

- Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.

- Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.

- Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.

- Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета. Если указан несуществующий стек, `Push-Location` создает стек.

- Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.

Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.
Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке. Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$Null` или пустой строкой ( `""` ).

Также можно ссылаться `Pop-Location` по встроенному псевдониму `popd` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

`Pop-Location` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Get-Location](Get-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
