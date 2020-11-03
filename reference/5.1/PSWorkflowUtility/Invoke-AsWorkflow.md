---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227342"
---
# Invoke-AsWorkflow

## Краткий обзор
Выполняет команду или выражение как рабочий процесс Windows PowerShell.

## SYNTAX

### Команда (по умолчанию)

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### Expression

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-AsWorkflow`Рабочий процесс запускает любую команду или выражение в качестве встроенного скрипта в рабочем процессе.
Эти рабочие процессы используют стандартную семантику рабочих процессов, имеют все общие параметры рабочих процессов и обладают всеми преимуществами рабочих процессов, включая возможность остановки, возобновления и восстановления.

Рабочие процессы предназначены для долго выполняющихся команд, которые осуществляют сбор критически важных данных, однако их можно использовать для выполнения любой команды.
Дополнительные сведения см. в разделе [about_Workflows](../PSWorkflow/About/about_Workflows.md).

В эту команду также можно добавить общие параметры рабочих процессов.
Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)

Этот рабочий процесс впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Запуск командлета в качестве рабочего процесса

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

Эта команда запускает `Get-ExecutionPolicy` командлет в качестве рабочего процесса на сотнях компьютеров.

Команда использует параметр **CommandName** , чтобы указать командлет, выполняемый в рабочем процессе.
Оно использует общий параметр **PSComputerName** рабочего процесса для указания компьютеров, на которых выполняется команда.
Значение параметра **PSComputerName** — это `Get-Content` команда, которая получает список имен компьютеров из файла Servers.txt.
Значение параметра заключается в круглые скобки, чтобы Windows PowerShell выполнял `Get-Command` команду перед использованием значения.

Как в случае со всеми удаленными командами, если команда выполняется на локальном компьютере (если локальный компьютер указан в значении параметра PSComputerName), необходимо запустить Windows PowerShell с помощью параметра "Запуск от имени администратора".

### Пример 2. Запуск командлета с параметрами

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

Первая команда использует `Import-Csv` командлет для создания объекта из содержимого в файле Servers.csv. Команда использует параметр, `Header` чтобы создать `ServerName` свойство для столбца, содержащего имена конечных компьютеров, также известные как "Удаленные узлы". Команда сохраняет результат в `$s` переменной.

Вторая команда использует `Invoke-AsWorkflow` Рабочий процесс для выполнения `Get-ExecutionPolicy` команды на компьютерах в Servers.csvном файле. Команда использует параметр **CommandName** параметра, `Invoke-AsWorkflow`  чтобы указать команду для выполнения в рабочем процессе. В нем используется `Parameter` параметр класса `Invoke-AsWorkflow` для указания `Scope` параметра `Get-ExecutionPolicy` командлета со значением **Process** . Команда также использует `PSConnectionRetryCount` общий параметр рабочего процесса, чтобы ограничить число попыток выполнения команды пятью попытками на каждом компьютере и `PSComputerName` общий параметр рабочего процесса, чтобы указать имена удаленных узлов (конечных компьютеров). Значение `PSComputerName` параметра является выражением, которое получает `ServerName` свойство каждого объекта в `$s` переменной.

Эти команды выполняют `Get-ExecutionPolicy` команду как рабочий процесс на сотнях компьютеров.
Команда использует `Scope` параметр `Get-ExecutionPolicy` командлета со значением **Process** , чтобы получить политику выполнения в текущем сеансе.

### Пример 3. Запуск выражения в качестве рабочего процесса

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

Эта команда использует `Invoke-AsWorkflow` Рабочий процесс для выполнения команды ipconfig в качестве задания рабочего процесса на компьютерах, перечисленных в файле DomainControllers.txt.

Команда использует параметр, `Expression` чтобы указать выражение для выполнения.
В нем используется `PSComputerName` общий параметр рабочего процесса для указания имен удаленных узлов (конечных компьютеров).

Команда также использует `AsJob` `JobName` Общие параметры рабочего процесса и для запуска рабочего процесса в качестве фонового задания на каждом компьютере с именем задания ipconfig.

Команда возвращает `ContainerParentJob` объект ( `System.Management.Automation.ContainerParentJob` ), содержащий задания рабочего процесса на каждом компьютере.

## PARAMETERS

### -CommandName

Выполняет указанный командлет или дополнительную функцию как рабочий процесс.
Введите имя командлета или функции, например `Update-Help` , `Set-ExecutionPolicy` или `Set-NetFirewallRule` .

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expression

Указывает выражение, выполняемое этим командлетом в качестве рабочего процесса.
Введите выражение в виде строки, например `"ipconfig /all"` .
Если выражение содержит пробелы или специальные символы, необходимо заключить его в кавычки.

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

Задает параметры и значения параметров команды, указанной в `CommandName` параметре.
Введите хэш-таблицу, в которой каждый ключ является именем параметра, а его значение — значением параметра, например `@{ExecutionPolicy="AllSigned"}` .

Дополнительные сведения о хэш-таблицах см. в разделе [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Используется, чтобы разрешить входные данные конвейера.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

### воркфловкоммонпараметерс

Этот командлет также поддерживает общие параметры рабочего процесса.
Дополнительные сведения см. в разделе [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).

## Входные данные

### System.Object

Любой объект можно передать в `InputObject` параметр.

## Выходные данные

### Нет

Эта команда не формирует никаких выходных данных.
Однако она запускает рабочий процесс, который может формировать выходные данные.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[New-PSWorkflowSession](../PSWorkflow/New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_Workflow_Common_Parameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)
