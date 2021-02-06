---
description: Описывает, как интерпретировать и отформатировать выходные данные удаленных команд.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 476afc62089795d22002ece05c7ce2bf53994237
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602841"
---
# <a name="about-remote-output"></a>Об удаленных выходных данных

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает, как интерпретировать и отформатировать выходные данные удаленных команд.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Выходные данные команды, запущенной на удаленном компьютере, могут выглядеть так, как выходные данные одной и той же команды выполняются на локальном компьютере, но существуют некоторые существенные различия.

В этом разделе объясняется, как интерпретировать, форматировать и отображать выходные данные команд, выполняемых на удаленных компьютерах.

## <a name="displaying-the-computer-name"></a>ОТОБРАЖЕНИЕ ИМЕНИ КОМПЬЮТЕРА

При использовании командлета Invoke-Command для выполнения команды на удаленном компьютере команда возвращает объект, содержащий имя компьютера, создавшего данные. Имя удаленного компьютера хранится в свойстве PSComputerName.

Для многих команд PSComputerName отображается по умолчанию. Например, следующая команда выполняет команду Get-Culture на двух удаленных компьютерах, Server01 и Server02. Выходные данные, показанные ниже, включают имена удаленных компьютеров, на которых выполнялась команда.

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

Чтобы скрыть свойство PSComputerName, можно использовать параметр Хидекомпутернаме Invoke-Command. Этот параметр предназначен для команд, собирающих данные только с одного удаленного компьютера.

Следующая команда выполняет команду Get-Culture на удаленном компьютере Server01. Для скрытия свойства PSComputerName и связанных свойств используется параметр Хидекомпутернаме.

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

Можно также отобразить свойство PSComputerName, если оно не отображается по умолчанию.

Например, следующие команды используют командлет Format-Table для добавления свойства PSComputerName в выходные данные удаленной команды Get-Date.

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a>ОТОБРАЖЕНИЕ СВОЙСТВА MACHINENAME

Несколько командлетов, в том числе Get-Process, Get-Service и Get-EventLog, имеют параметр ComputerName, который получает объекты на удаленном компьютере.
Эти командлеты не используют удаленное взаимодействие PowerShell, поэтому их можно использовать даже на компьютерах, которые не настроены для удаленного взаимодействия в Windows PowerShell.

Объекты, возвращаемые этими командлетами, сохраняют имя удаленного компьютера в свойстве MachineName. (Эти объекты не имеют свойства PSComputerName.)

Например, эта команда получает процесс PowerShell на удаленных компьютерах Server01 и Server02. Отображение по умолчанию не включает свойство MachineName.

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

Для вывода свойства MachineName объектов процесса можно использовать командлет Format-Table.

Например, следующая команда сохраняет процессы в переменной $p, а затем использует оператор конвейера (|) для отправки процессов в $p команде Format-Table. Команда использует параметр Property объекта Format-Table для включения свойства MachineName в экран.

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

Следующая более сложная команда добавляет свойство MachineName к отображению процесса по умолчанию. Для указания вычисляемых свойств используются хэш-таблицы. К счастью, вам не нужно понимать, что его использовать.

(Обратите внимание, что Обратная кавычка ['] является символом продолжения.)

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a>ДЕСЕРИАЛИЗОВАННЫЕ ОБЪЕКТЫ

При выполнении удаленных команд, которые формируют выходные данные команды, передаются по сети обратно на локальный компьютер.

Так как большинство объектов Microsoft .NET Framework (например, объекты, возвращаемые командлетами PowerShell) не могут передаваться по сети, объекты в реальном времени сериализуются. Иными словами, активные объекты преобразуются в XML-представления объекта и его свойств. Затем сериализованный объект на основе XML передается по сети.

На локальном компьютере PowerShell получает сериализованный объект на основе XML и десериализует его путем преобразования объекта на основе XML в стандартный объект платформа .NET Framework.

Однако десериализованный объект не является активным объектом. Он является моментальным снимком объекта во время его сериализации и содержит свойства, но не имеет методов. Вы можете использовать эти объекты и управлять ими в PowerShell, в том числе передавать их в конвейеры, отображая выбранные свойства и форматировать их.

Большинство десериализованных объектов автоматически отформатированы для показа записями в Types.ps1XML-или Format.ps1XML-файлах. Однако на локальном компьютере могут отсутствовать файлы форматирования для всех десериализованных объектов, созданных на удаленном компьютере. Если объекты не отформатированы, все свойства каждого объекта отображаются в консоли в списке потоковой передачи.

Если объекты не отформатированы автоматически, можно использовать командлеты форматирования, такие как Format-Table или Format-List, для форматирования и вывода выбранных свойств. Также можно использовать командлет Out-GridView для вывода объектов в таблице.

Кроме того, при выполнении команды на удаленном компьютере, использующем командлеты, которых нет на локальном компьютере, объекты, возвращаемые командой, могут быть неправильно отформатированы, так как у вас нет файлов форматирования для этих объектов на компьютере. Чтобы получить данные форматирования с другого компьютера, используйте командлеты Get-FormatData и Export-FormatData.

Некоторые типы объектов, например объекты DirectoryInfo и GUID, преобразуются обратно в динамические объекты при их получении. Для этих объектов не требуется специальная обработка или форматирование.

## <a name="ordering-the-results"></a>УПОРЯДОЧИВАНИЕ РЕЗУЛЬТАТОВ

Порядок имен компьютеров в параметре ComputerName командлетов определяет порядок, в котором PowerShell подключается к удаленным компьютерам. Однако результаты отображаются в порядке, в котором локальный компьютер получает их, что может отличаться от порядка.

Чтобы изменить порядок результатов, используйте командлет Sort-Object. Можно выполнить сортировку по свойству PSComputerName или MachineName. Можно также выполнить сортировку по другому свойству объекта, чтобы результаты с разных компьютеров были смешанными.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Get-Process](xref:Microsoft.PowerShell.Management.Get-Process)

[Get-Service](xref:Microsoft.PowerShell.Management.Get-Service)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

