---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227453"
---
# Test-DscConfiguration

## Краткий обзор
Проверяет, соответствует ли фактическая конфигурация на узлах требуемой.

## SYNTAX

### Компутернамесет (по умолчанию)

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### компутернамеандпассет

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### компутернамеандреференцеконфигуратионсет

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### Цимсессионандпассет

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### Цимсессионандреференцеконфигуратионсет

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### Цимсессионсет

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Test-DscConfiguration** проверяет, соответствует ли фактическая конфигурация на узлах требуемой.
Укажите компьютеры, для которых требуется проверить конфигурации, используя имена компьютеров или сеансы модель CIM (CIM).
Если целевой компьютер не указан, командлет проверяет конфигурацию локального компьютера.

Если требуемые и фактические конфигурации совпадают, командлет возвращает строковое значение "true".
В противном случае возвращается строковое значение "false".

## Примеры

### Пример 1. Конфигурация теста для локального компьютера

```
PS C:\> Test-DscConfiguration
```

Эта команда проверяет конфигурацию для локального компьютера.

### Пример 2. Конфигурация теста для указанного компьютера

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

В этом примере проверяется конфигурация компьютера, указанного сеансом CIM.
Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.
Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.

Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.
Команда запрашивает пароль.
Для получения дополнительных сведений введите `Get-Help New-CimSession`.

Вторая команда проверяет конфигурацию компьютеров, определенных объектами **CimSession** , сохраненными в переменной $Session, в данном случае — для компьютера с именем Server01.

### Пример 3. тестовые конфигурации с подробными результатами

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

Эта команда проверяет конфигурации для набора компьютеров, указанных параметром *ComputerName* , и возвращает подробные сведения, включающие в себя общее состояние, ресурсы, которые находятся в нужном состоянии, ресурсы, которые не находятся в нужном состоянии и имя компьютера.

### Пример 4. конфигурации тестов, указанные в папке

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

Эта команда проверяет конфигурации, определенные в папке, указанной параметром *path* .
Конфигурации проверяются на наборе компьютеров, каждый из которых определяется по имени файла конфигурации.

### Пример 5. конфигурации тестов, указанные в файле

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

Эта команда проверяет конфигурацию, определенную в файле, по набору компьютеров, заданному параметром *ComputerName* .

## PARAMETERS

### -AsJob
Указывает, что этот командлет выполняет команду как фоновое задание.

Если указать параметр *AsJob* , команда возвращает объект, представляющий задание, а затем появляется командная строка.
Вы можете продолжить работу в рамках данного сеанса, пока задание не будет завершено.
Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.
Для управления заданием используйте командлеты Job.
Чтобы получить результаты задания, используйте командлет Receive-Job.

Чтобы использовать этот параметр, локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия, а в Windows Vista и более поздних версиях операционной системы Windows необходимо также запустить Windows PowerShell от имени администратора.
Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

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

### -CimSession
Запуск командлета в удаленном сеансе или на удаленном компьютере.
Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
Сеанс по умолчанию — текущий сеанс на локальном компьютере.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Указывает массив имен компьютеров, на которых этот командлет проверяет конфигурацию.
Командлет проверяет документ конфигурации в расположении, указанном параметром *path* , для этих компьютеров.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
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
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
Указывает, что этот командлет возвращает подробный результат сравнения документа конфигурации с требуемым состоянием узлов.
Результат включает такие сведения, как общее состояние, ресурсы, которые находятся в требуемом состоянии, ресурсы, которые не находятся в требуемом состоянии, и имя компьютера.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Указывает путь к папке, содержащей файлы документов конфигурации.
Командлет проверяет конфигурацию на соответствие требуемому состоянию компьютеров, указанных параметром *ComputerName* или *CimSession* .

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Референцеконфигуратион
Указывает путь к файлу документа конфигурации.
Этот командлет проверяет конфигурацию на соответствие фактическому состоянию компьютеров, указанных параметром *ComputerName* или *CimSession* .

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)
