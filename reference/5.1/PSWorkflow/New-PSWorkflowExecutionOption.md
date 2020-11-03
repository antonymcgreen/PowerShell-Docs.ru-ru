---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229809"
---
# New-PSWorkflowExecutionOption

## Краткий обзор

Создает объект, содержащий параметры конфигурации сеанса для сеансов рабочего процесса.

## SYNTAX

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`New-PSWorkflowExecutionOption`Командлет создает объект, который содержит дополнительные параметры для конфигураций сеанса рабочего процесса, которые являются конфигурациями сеансов, предназначенными для запуска рабочих процессов Windows PowerShell.

Можно использовать объект **PSWorkflowExecutionOption** , который `New-PSWorkflowExecutionOption` создает в качестве значения параметра **сессионтипеоптион** командлетов, которые создают или изменяют конфигурацию сеанса, например `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` командлеты и.

Каждый параметр `New-PSWorkflowExecutionOption` командлета представляет свойство объекта параметра конфигурации сеанса рабочего процесса, возвращаемого командлетом. Если параметр не указан, командлет создает для свойства объект со значением по умолчанию.

`New-PSWorkflowExecutionOption`Командлет является частью компонента рабочего процесса Windows PowerShell.

В эту команду также можно добавить общие параметры рабочих процессов. Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание объекта параметров рабочего процесса

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

Эта команда использует `New-PSWorkflowExecutionOption` командлет, чтобы увеличить значение **макссессионсперворкфлов** до 10 и уменьшить значение **максдисконнектедсессионс** до 200.

Выходные данные показывают объект, возвращаемый командлетом.

### Пример 2. Использование объекта параметров рабочего процесса

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

Первые две команды создают новый объект конфигурации сеанса и регистрируют его.

Третья команда использует `Get-PSSessionConfiguration` командлет для получения конфигурации сеанса итворкфловс и `Format-List` для вывода всех свойств конфигурации сеанса в списке. Выходные данные показывают, что параметры рабочего процесса в конфигурации сеанса. В частности, конфигурации сеанса имеет свойство **MaxSessionsPerWorkflow** со значением 10 и свойство **MaxDisconnectedSessions** со значением 200.

## PARAMETERS

### -ActivityProcessIdleTimeoutSec

Определяет, как долго сохраняется каждый хост-процесс действия после того, как процесс становится неактивным. По истечении периода процесс закрывается.

Введите значение в секундах. Значение по умолчанию — 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedActivity

Указывает действия, которые можно выполнять в сеансе.

Введите имена действий, уточненные пространством имен, например `Microsoft.Powershell.HyperV.Activities.*` .
Поддерживаются подстановочные знаки. Значение по умолчанию **PSDefaultActivities** включает в себя встроенные действия Windows Workflow Foundation и действия, представляющие основные командлеты Windows PowerShell.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableValidation

Проверяет, что все действия рабочих процессов в сеансе включены в список разрешенных действий.

По умолчанию используется значение True. Чтобы отключить проверку, используйте следующий формат команды: `-EnableValidation:$false`.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxActivityProcesses

Указывает максимальное число процессов, которые могут быть созданы в сеансе для поддержки действий рабочего процесса. Значение по умолчанию — 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxConnectedSessions

Указывает максимальное количество удаленных сеансов, находящихся в рабочем состоянии. Эта квота применяется к сеансам, подключенным ко всем удаленным узлам (конечным компьютерам). По умолчанию используется значение 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxDisconnectedSessions

Указывает максимальное количество удаленных сеансов, находящихся в отключенном состоянии. Эта квота применяется к сеансам, подключенным ко всем удаленным узлам (конечным компьютерам). Значение по умолчанию ― 1000.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPersistenceStoreSizeGB

Указывает максимальный размер (в ГБ) хранилища сохраняемости, выделенного для выполняемых в сеансе рабочих процессов. При превышении размера хранилище расширяется, чтобы сохранить все сохраненные данные, но при этом отображается предупреждение и в журнал событий рабочего процесса записывается сообщение. Значение по умолчанию — 10.

Хранилище сохраняемости содержит данные обо всех заданиях рабочего процесса. Возможность хранения данных позволяет возобновить задания без потери состояния.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRunningWorkflows

Указывает максимальное число рабочих процессов, которые могут выполняться в сеансе одновременно.
Значение по умолчанию — 30.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessionsPerRemoteNode

Указывает максимальное количество сеансов, которые могут быть подключены к каждому удаленному узлу (конечному компьютеру). Значение по умолчанию — 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessionsPerWorkflow

Указывает максимальное количество сеансов, которые можно создать для поддержки каждого рабочего процесса. Значение по умолчанию — 5.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutOfProcessActivity

Определяет, какие разрешенные действия (указанные параметром **AllowedActivities** ) выполняются вне процесса. Значение по умолчанию — **InlineScript**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistencePath

Указывает расположение на диске, где хранится состояние рабочего процесса и данные. Хранение данных и состояния рабочего процесса позволяет приостанавливать и возобновлять рабочие процессы, а также восстанавливать работу после нарушений и сетевых ошибок.

Значение по умолчанию — `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistWithEncryption

Указывает, что рабочий процесс шифрует данные в хранилище сохраняемости. Рекомендуется использовать эту функцию при хранении данных сохраняемости в общей сетевой папке.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteNodeSessionIdleTimeoutSec

Указывает продолжительность поддержки работоспособности сеанса, который подключен к удаленному узлу (конечному компьютеру), в случае бездействия.

Введите значение в секундах. Значение по умолчанию — 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionThrottleLimit

Указывает, сколько операций создается для поддержки всех рабочих процессов, запущенных в рамках сеанса. По умолчанию используется значение 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkflowShutdownTimeoutMSec

Указывает продолжительность поддержки работоспособности сеанса после принудительной приостановки всех рабочих процессов в сеансе. По истечении этого времени Windows PowerShell закрывает сеанс, даже если еще не приостановлены все рабочие процессы.

Введите значение в миллисекундах.
Значение по умолчанию — 500.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft.PowerShell.Commands.PSWorkflowExecutionOption

## ПРИМЕЧАНИЯ

При превышении максимального значения, заданного параметром, команда на создание другого экземпляра в сеансе завершается ошибкой, если это не прописано в описании параметра. Например, если значение **MaxConnectedSessions** равно 100. Команда на создание 101-го сеанса с удаленным узлом (конечным компьютером) завершается с ошибкой.

Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

В частности, свойства конфигурации сеанса, включающие в себя объект **PSWorkflowExecutionOptions** , зависят от значений параметров рабочего процесса. Например, если конфигурация сеанса включает в себя объект **PSWorkflowExecutionOptions** , который задает нестандартное значение для свойства **SessionThrottleLimit** , конфигурация сеанса имеет свойство **SessionThrottleLimit**. В противном случае это условие не выполняется.

## Связанные ссылки

[New-PSWorkflowSession](New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
