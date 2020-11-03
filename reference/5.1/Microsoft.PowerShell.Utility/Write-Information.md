---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: e0f28393c95e2c0703c489d4691edcf883b4cb05
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232814"
---
# Write-Information

## Краткий обзор

Указывает, как PowerShell обрабатывает данные информационного потока для команды.

## SYNTAX

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Write-Information`Командлет определяет, как PowerShell обрабатывает данные информационного потока для команды.

В Windows PowerShell 5,0 появился новый структурированный информационный поток. Этот поток можно использовать для передачи структурированных данных между скриптом и его вызывающими объектами или ведущим приложением.
`Write-Information` позволяет добавить информационное сообщение в поток и указать, как PowerShell обрабатывает данные информационного потока для команды. Информационные потоки также работают для `PowerShell.Streams` , заданий и запланированных задач.

> [!NOTE]
> Информационный поток не соответствует стандартному соглашению о предисправлении сообщений с помощью "[Stream name]:". Это было предназначено для краткости и Visual чистоте.

`$InformationPreference`Значение переменной предпочтения определяет, отображается ли сообщение, которое вы указываете, в `Write-Information` ожидаемой точке операции скрипта. Поскольку значение по умолчанию для этой переменной равно `SilentlyContinue` , по умолчанию информационные сообщения не отображаются. Если вы не хотите изменять значение `$InformationPreference` , его значение можно переопределить, добавив в `InformationAction` команду Общий параметр. Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) и [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

> [!NOTE]
> Начиная с Windows PowerShell 5,0, `Write-Host` — это оболочка для этого, которая `Write-Information` позволяет использовать `Write-Host` для отправки выходных данных в информационный поток. Это позволяет **записывать** или **подавить** данные, написанные с помощью, сохраняя `Write-Host` обратную совместимость. Дополнительные сведения см. в разделе [Write-Host](Write-Host.md) .

`Write-Information` также является поддерживаемым действием рабочего процесса в PowerShell 5. x.

## Примеры

### Пример 1. запись сведений для Get-Results

В этом примере отображается информационное сообщение "получены ваши компоненты!" после выполнения `Get-WindowsFeature` команды, чтобы найти все компоненты, имя которых начинается с "p".
Так как `$InformationPreference` переменная по-прежнему имеет значение по умолчанию, `SilentlyContinue` вы добавляете `InformationAction` параметр для переопределения `$InformationPreference` значения и отображает сообщение. Значение Continue, означающее, что `InformationAction` сообщение отображается, но скрипт или команда продолжают работу, если она еще не завершена.

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### Пример 2. запись сведений и пометка их

В этом примере вы будете использовать, `Write-Information` чтобы сообщить пользователям, что им потребуется выполнить другую команду после выполнения текущей команды. В этом примере в информационное сообщение добавляются инструкции тегов. После выполнения этой команды при поиске в информационном потоке инструкций, помеченных как сообщения, указанное здесь сообщение будет среди результатов.

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### Пример 3. запись сведений в файл

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

## PARAMETERS

### -MessageData

Указывает информационное сообщение, которое будет отображаться для пользователей при выполнении сценария или команды. Для достижения лучших результатов заключите информационное сообщение в кавычки.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Теги

Задает простую строку, которую можно использовать для сортировки и фильтрации сообщений, добавленных в информационный поток в `Write-Information` . Этот параметр работает аналогично параметру **Tags** в `New-ModuleManifest` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

`Write-Information` не принимает входные данные о перенаправлении.

## Выходные данные

### System. Management. Automation. Информатионрекорд

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)

[Write-Output](Write-Output.md)
