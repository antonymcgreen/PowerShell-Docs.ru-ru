---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 85cbc9d012781873dddaf2a7d220a0e478dcbda2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601604"
---
# Enter-PSHostProcess

## Краткий обзор
Подключается к интерактивному сеансу с локальным процессом и входит в него.

## SYNTAX

### Процессидпараметерсет (по умолчанию)

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### процесспараметерсет

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### процесснамепараметерсет

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### пшостпроцессинфопараметерсет

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### пипенамепараметерсет

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## DESCRIPTION

`Enter-PSHostProcess`Командлет подключается к интерактивному сеансу с локальным процессом и входит в него. Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.

Вместо создания нового процесса для размещения PowerShell и запуска удаленного сеанса удаленный интерактивный сеанс выполняется в существующем процессе, который уже выполняет PowerShell. При взаимодействии с удаленным сеансом в указанном процессе можно выполнить перечисление выполняющихся пространств выполнения, а затем выбрать пространство выполнения для отладки, выполнив команду `Debug-Runspace` или `Enable-RunspaceDebug` .

В процессе, который необходимо ввести, должен быть размещен PowerShell (System.Management.Automation.dll).
Необходимо быть членом группы администраторов на компьютере, где находится процесс, или пользователь, выполняющий сценарий, запустивший процесс.

После выбора пространства выполнения для отладки для пространства выполнения будет открыт сеанс удаленной отладки, если в данный момент он выполняет команду или остановлен в отладчике. Затем можно выполнить отладку скрипта пространства выполнения так же, как при отладке других сценариев удаленного сеанса.

Отсоединитесь от сеанса отладки, а затем интерактивный сеанс с процессом, выполнив команду Exit дважды или остановите выполнение скрипта, запустив имеющуюся кнопку Quit отладчика.

Если указать процесс с помощью параметра **Name** и обнаружен только один процесс с указанным именем, то будет введен процесс. Если найдено более одного процесса с указанным именем, PowerShell возвращает ошибку и перечисляет все обнаруженные процессы с указанным именем.

Для поддержки присоединения к процессам на удаленных компьютерах `Enter-PSHostProcess` командлет включен на указанном удаленном компьютере, чтобы можно было подключиться к локальному процессу в удаленном сеансе PowerShell.

## Примеры

### Пример 1. Начало отладки пространства выполнения в процессе интегрированной среды сценариев PowerShell

В этом примере вы запускаете `Enter-PSHostProcess` из консоли PowerShell, чтобы войти в процесс интегрированной среды сценариев PowerShell. В итоговом интерактивном сеансе можно найти пространство выполнения, которое необходимо отладить, выполнив `Get-Runspace` , а затем отладить пространство выполнения.

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## PARAMETERS

### -Аппдомаиннаме

Указывает имя домена приложения для подключения, если оно не указано, использует **дефаултаппдомаин**. Используется `Get-PSHostProcessInfo` для вывода имен доменов приложений.

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хостпроцессинфо

Указывает объект **PSHostProcessInfo** , к которому можно подключиться с помощью PowerShell. Используйте `Get-PSHostProcessInfo` для получения объекта.

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Указывает процесс по ИДЕНТИФИКАТОРу процесса. Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает процесс по имени процесса. Чтобы получить имя процесса, выполните `Get-Process` командлет. Имена процессов также можно получить из диалогового окна Свойства процесса в диспетчере задач.

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Process

Указывает процесс в объекте процесса. Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Кустомпипенаме

Возвращает или задает имя настраиваемого именованного канала для подключения. Обычно это используется в сочетании с `pwsh -CustomPipeName` .

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Diagnostics.Process

## Выходные данные

## ПРИМЕЧАНИЯ

`Enter-PSHostProcess` невозможно ввести процесс сеанса PowerShell, в котором выполняется команда. Однако можно ввести процесс другого сеанса PowerShell или сеанса интегрированной среды сценариев PowerShell, который выполняется в то же время, что и сеанс, в котором выполняется `Enter-PSHostProcess` .

`Enter-PSHostProcess` может вводить только процессы, в которых размещается PowerShell. То есть они загрузили подсистему PowerShell.

Чтобы выйти из процесса в процессе, введите команду **Exit** и нажмите клавишу <kbd>Ввод</kbd>.

До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком. Эта возможность была ограничена сеансами через WinRM. PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.

## Связанные ссылки

[Exit-PSHostProcess](Exit-PSHostProcess.md)

[Get-PSHostProcessInfo](Get-PSHostProcessInfo.md)

