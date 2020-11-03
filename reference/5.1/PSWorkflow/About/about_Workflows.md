---
description: Краткое введение в функцию рабочего процесса PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231589"
---
# <a name="about-workflows"></a>О рабочих процессах

## <a name="short-description"></a>Краткое описание

Краткое введение в функцию рабочего процесса PowerShell.

## <a name="long-description"></a>Подробное описание

Рабочий процесс PowerShell предоставляет преимущества [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) в PowerShell и позволяет создавать и запускать рабочие процессы.

Рабочий процесс PowerShell появился в PowerShell 3,0, а модуль доступен для PowerShell 5,1. Дополнительные сведения о рабочем процессе PowerShell см. в [руководствах по рабочим](/previous-versions/powershell/scripting/components/workflows-guide) процессам и [написании рабочего процесса Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).

## <a name="about-workflows"></a>О рабочих процессах

Рабочие процессы — это команды, состоящие из упорядоченной последовательности связанных действий. Как правило, они выполняются в течение продолжительного периода времени, сбор данных и внесение изменений в сотни компьютеров, часто в разнородных средах.

Рабочие процессы можно написать на языке XAML, на языке, используемом в Windows Workflow Foundation, или на языке PowerShell. Рабочие процессы обычно упаковываются в модули и включают разделы справки. Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).

Рабочие процессы являются критически важными в ИТ-среде, так как они могут выдерживать перезагрузку и автоматически восстанавливать из распространенных сбоев. Вы можете отключить и повторно подключиться к сеансам и компьютерам, на которых выполняются рабочие процессы, не прерывая обработку рабочего процесса, а также приостанавливать и возобновлять рабочие процессы без потери данных. Каждое действие в рабочем процессе можно регистрировать и подвергать аудиту для справки.
Рабочие процессы можно запускать в качестве заданий и планировать с помощью функции запланированных заданий PowerShell.

Состояние и данные в рабочем процессе сохраняются или сохраняются в начале и в конце рабочего процесса и в указанных точках. Точки сохранения рабочих процессов работают подобно моментальным снимкам базы данных или программам, чтобы защитить рабочий процесс от влияния прерываний и сбоев. Если рабочему процессу не удается выполнить восстановление после сбоя, можно использовать сохраненные данные и возобновить работу из последней точки сохранения, а не выполнять большой рабочий процесс с самого начала.

## <a name="workflow-requirements-and-configuration"></a>Требования и конфигурация рабочего процесса

Конфигурация рабочего процесса PowerShell состоит из следующих элементов:

- Клиентский компьютер, на котором выполняется рабочий процесс.
- Сеанс рабочего процесса **PSSession** на клиентском компьютере или на удаленном компьютере.
- Управляемые узлы — целевые компьютеры, на которые влияют действия рабочего процесса.

Сеанс рабочего процесса не требуется, но рекомендуется. **PSSession** может воспользоваться возможностями надежного восстановления и отключенных сеансов PowerShell для восстановления отключенных сеансов рабочих процессов. Дополнительные сведения см. в разделе [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)

Так как клиентский компьютер и компьютер, на котором выполняется сеанс рабочего процесса, могут быть управляемыми узлами, Рабочий процесс можно запустить на одном компьютере, выполняющем все роли.

Клиентский компьютер и компьютер, на котором запущен сеанс рабочего процесса, должны работать под управлением PowerShell 3,0. Поддерживаются все подходящие системы, включая варианты установки основных серверных компонентов для операционных систем Windows Server.

Для запуска рабочих процессов, включающих командлеты, на управляемых узлах должен быть установлен Windows PowerShell 2,0 или более поздней версии. Управляемые узлы не нуждаются в PowerShell, если только рабочий процесс не включает командлеты. Рабочие процессы, содержащие команды инструментарий управления Windows (WMI) (WMI) и модель CIM (CIM), можно запускать на компьютерах без PowerShell.

## <a name="how-to-get-workflows"></a>Как получить рабочие процессы

Рабочие процессы обычно упаковываются в модули. Чтобы импортировать модуль, включающий рабочий процесс, используйте любую команду в модуле или используйте `Import-Module` командлет.
Модули импортируются автоматически при первом использовании любой команды в модуле.

Чтобы найти рабочие процессы в модулях, установленных на компьютере, используйте `Get-Command` параметр **CommandType** командлета.

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a>Запуск рабочих процессов

Для запуска рабочего процесса используйте следующую процедуру.

1. Если управляемый узел является локальным компьютером, этот шаг не требуется.
   В противном случае на клиентском компьютере запустите PowerShell с параметром **Запуск от имени администратора** .

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. Включите удаленное взаимодействие PowerShell на компьютере, на котором запущен сеанс рабочего процесса, и на управляемых узлах, затронутых рабочими процессами, включающими командлеты.

   Этот шаг необходимо выполнить только один раз на каждом компьютере, участвующем в работе.

   Этот шаг необходим только при выполнении рабочих процессов, включающих командлеты. Не требуется включать удаленное взаимодействие на клиентском компьютере, если сеанс рабочих процессов не выполняется на клиентском компьютере или на управляемых узлах, на которых выполняется PowerShell 3,0.

   Чтобы включить удаленное взаимодействие, используйте `Enable-PSRemoting` командлет.

   ```powershell
   Enable-PSRemoting -Force
   ```

   Включить удаленное взаимодействие можно с помощью параметра **включить выполнение скрипта** групповая политика. Дополнительные сведения см. в разделе [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) и [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

1. Используйте `New-PSWorkflowSession` `New-PSSession` командлеты или для создания сеанса рабочего процесса.

   `New-PSWorkflowSession`Командлет запускает сеанс, использующий встроенную конфигурацию сеанса **Microsoft. PowerShell. Workflow** на конечном компьютере. Эта конфигурация сеанса включает в себя сценарии, файлы типов и форматирования, а также параметры, предназначенные для рабочих процессов.

   Или используйте `New-PSSession` командлет. Используйте параметр **configurationName** , чтобы указать конфигурацию сеанса **Microsoft. PowerShell. Workflow** . Эта команда аналогична использованию `New-PSWorkflowSession` командлета.

   Альтернативой является использование `New-PSSession` командлета. Используйте параметр **configurationName** , чтобы указать конфигурацию сеанса **Microsoft. PowerShell. Workflow** .

   На локальном компьютере:

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   На удаленном компьютере:

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   Если вы являетесь администратором на компьютере сеанса рабочего процесса, можно использовать `New-PSWorkflowExecutionOption` командлет для создания настраиваемых параметров для конфигурации сеанса рабочего процесса. И с помощью `Set-PSSessionConfiguration` командлета измените конфигурацию сеанса.

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. Запустите рабочий процесс в сеансе рабочего процесса. Чтобы указать имена управляемых узлов (конечных компьютеров), используйте общий параметр рабочего процесса **PSComputerName** .

   В следующих примерах выполняется рабочий процесс с именем **Test-Workflow**.

   Где управляемый узел — это компьютер, на котором размещается сеанс рабочего процесса:

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   Где управляемые узлы являются удаленными компьютерами.

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   В следующем примере запускается **тестовый рабочий процесс** на сотнях компьютеров. `Get-Content`Командлет получает имена компьютеров из текстового файла и сохраняет их в `$Servers` переменной на локальном компьютере.

   `Invoke-Command` использует `$Using` Модификатор области для определения `$Servers` переменной в локальном сеансе. Дополнительные сведения об `$Using` модификаторе области см. в разделе [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a>Использование общих параметров рабочего процесса

Общие параметры рабочего процесса — это набор параметров, которые PowerShell автоматически добавляет ко всем рабочим процессам. PowerShell добавляет общие параметры командлета для всех рабочих процессов, даже если рабочий процесс не использует атрибут **CmdletBinding** .

Например, следующий рабочий процесс не определяет параметры. Однако при запуске рабочего процесса у него есть и **общиепараметры** , и **воркфловкоммонпараметерс**.

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

Общие параметры рабочего процесса включают несколько параметров, необходимых для выполнения рабочих процессов. Например, общий параметр **PSComputerName** указывает управляемые узлы, на которые влияет рабочий процесс.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

Общий параметр рабочего процесса **псперсист** определяет, когда сохраняются данные рабочего процесса. Он позволяет добавлять точки сохранения между действиями в рабочие процессы, которые не определяют точки сохраняемости.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

Другие общие параметры рабочего процесса позволяют указать характеристики удаленного подключения к управляемым узлам. Их имена и функциональные возможности похожи на параметры командлетов удаленного взаимодействия, включая `Invoke-Command` .

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

Следите за тем, чтобы отличать параметры удаленного взаимодействия, определяющие подключение для сеанса рабочего процесса, из общих параметров рабочего процесса с **префиксом PS** , определяющих соединение с управляемыми узлами.

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

Некоторые общие параметры рабочего процесса являются уникальными для рабочих процессов, например параметр **пспараметерколлектион** , позволяющий указывать различные значения общих параметров рабочего процесса для разных удаленных узлов. Список и описание общих параметров рабочего процесса см. в разделе [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).

## <a name="see-also"></a>См. также статью

[Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

Командлеты [PSWorkflow](xref:PSWorkflow)

[Руководство по рабочим процессам](/previous-versions/powershell/scripting/components/workflows-guide)

[Запись рабочего процесса Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
