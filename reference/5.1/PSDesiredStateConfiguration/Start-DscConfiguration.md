---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228309"
---
# Start-DscConfiguration

## Краткий обзор
Применяет конфигурацию к узлам.

## SYNTAX

### Компутернамеандпассет (по умолчанию)

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Цимсессионандпассет

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### компутернамеандусиксистингсет

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Цимсессионандусиксистингсет

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Start-DscConfiguration** применяет конфигурацию к узлам.
При использовании с параметром *UseExisting* применяется существующая конфигурация на целевом компьютере.
Укажите компьютеры, к которым требуется применить конфигурацию, указав имена компьютеров или используя сеансы модель CIM (CIM).

По умолчанию этот командлет создает задание и возвращает объект **Job** .
Для получения дополнительных сведений о фоновых заданиях введите `Get-Help about_Jobs` .
Чтобы использовать этот командлет в интерактивном режиме, укажите параметр *Wait* .

Задайте параметр *Verbose* , чтобы посмотреть сведения о действиях командлета при применении параметров конфигурации.

## Примеры

### Пример 1. применение параметров конфигурации

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

Эта команда применяет параметры конфигурации из каталога C:\DSC\Configurations\ ко всем компьютерам, имеющим параметры в этой папке.
Команда возвращает объекты **Job** для каждого целевого узла, в котором они развернуты.

### Пример 2. применение параметров конфигурации и ожидание завершения настройки

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

Эта команда применяет конфигурацию из каталога C:\DSC\Configurations\ к локальному компьютеру.
Команда возвращает объекты **Job** для каждого целевого узла, в котором они развернуты (в данном случае просто  локальный компьютер).
В этом примере задается параметр *verbose* .
Таким образом, команда отправляет сообщения на консоль по мере продолжения.
Команда включает параметр *Wait* .
Поэтому вы не можете использовать консоль, пока команда не завершит все задачи настройки.

### Пример 3. применение параметров конфигурации с помощью сеанса CIM

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

В этом примере к указанному компьютеру применяются параметры конфигурации.
Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.
Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.

Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.
Команда запрашивает пароль.
Для получения дополнительных сведений введите `Get-Help NewCimSession`.

Вторая команда применяет параметры конфигурации из каталога c:\dsc\configurations\ к компьютерам, идентифицируемым объектами **CimSession** , хранящимися в переменной $Session.
В этом примере переменная $Session содержит сеанс CIM только для компьютера с именем Server01.
Команда применяет конфигурацию.
Команда создает объекты **Job** для каждого настроенного компьютера.

## PARAMETERS

### -CimSession
Запуск командлета в удаленном сеансе или на удаленном компьютере.
Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
Сеанс по умолчанию — текущий сеанс на локальном компьютере.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Указывает массив имен компьютеров.
Этот параметр позволяет ограничивать компьютеры, на которых имеются документы конфигурации в параметре *path* , на указанные в массиве.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.
Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.
Для получения дополнительных сведений введите `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Останавливает операцию настройки, которая выполняется на целевом компьютере, и начинает новую операцию Start-Configuration.
Если свойство **RefreshMode** локального Configuration Manager имеет значение **Pull** , то при указании этого параметра он изменяется на **Push** .

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

### -JobName
Задает понятное имя для задания.
Если указать этот параметр, командлет выполняется как задание и возвращает объект **Job** .

По умолчанию Windows PowerShell назначает имя Жобн, где N — целое число.

Если параметр *Wait* указан, не указывайте этот параметр.

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

### -Path
Указывает путь к файлу папки, которая содержит файлы параметров конфигурации.
Этот командлет публикует и применяет эти параметры конфигурации к компьютерам, имеющим файлы параметров по указанному пути.
Каждый целевой узел должен иметь файл параметров следующего формата: NetBIOS Name. mof.

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.
Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.
Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.

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

### -UseExisting
Указывает, что этот командлет применяет существующую конфигурацию.
Конфигурация может существовать на целевом компьютере путем внедрения с помощью командлета **Start-DscConfiguration** или публикации с помощью Publish-DscConfiguration.

Прежде чем указать этот параметр для этого командлета, ознакомьтесь со сведениями в подразделах [что нового в Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Указывает, что командлет блокирует консоль до тех пор, пока не завершит все задачи настройки.

Если этот параметр указан, не указывайте параметр *JobName* .

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

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/overview)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)
