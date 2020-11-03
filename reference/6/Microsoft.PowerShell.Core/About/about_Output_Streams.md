---
description: Объясняет доступность и назначение выходных потоков в PowerShell.
keywords: PowerShell, командлет
Locale: en-US
ms.date: 10/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_output_streams?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Output_Streams
ms.openlocfilehash: eca231bf9fae9fdf84dd0dc34f2e1a6fc189279e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232786"
---
# <a name="about-output-streams"></a>О выходных потоках

## <a name="short-description"></a>Краткое описание
Объясняет доступность и назначение выходных потоков в PowerShell.

## <a name="long-description"></a>Подробное описание

PowerShell предоставляет несколько выходных потоков. Потоки предоставляют каналы для различных типов сообщений. Вы можете записывать данные в эти потоки с помощью связанного командлета или перенаправления. Дополнительные сведения см. в разделе [about_Redirection](about_Redirection.md).

PowerShell поддерживает следующие выходные потоки.

| Вышестоящий # |      Описание       | Введено в  |    Записать командлет     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | **Успешно выполненный** поток     | PowerShell 2.0 | `Write-Output`      |
| 2        | Поток **ошибок**       | PowerShell 2.0 | `Write-Error`       |
| 3        | Поток **предупреждений**     | PowerShell 3.0 | `Write-Warning`     |
| 4        | **Подробный** поток     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | **Отладка** потока       | PowerShell 3.0 | `Write-Debug`       |
| 6        | **Информационный** поток | PowerShell 5.0 | `Write-Information` |
| Н/Д      | Поток **хода выполнения**    | PowerShell 3.0 | `Write-Progress`    |

> [!NOTE]
> Поток **хода выполнения** не поддерживает перенаправление.

## <a name="success-stream"></a>Успешно выполненный поток

Поток **Success** — это поток по умолчанию для обычных, успешных результатов.
Используйте `Write-Output` командлет для явного записи объектов в этот поток. Этот поток используется для передачи объектов через конвейер PowerShell. Поток **успешного выполнения** подключается к потоку **stdout** для собственных приложений.

## <a name="error-stream"></a>Поток ошибок

Поток **ошибок** является потоком по умолчанию для результатов ошибок. Используйте `Write-Error` командлет для явной записи в этот поток. Поток **ошибок** подключен к потоку **stderr** для собственных приложений. В большинстве случаев эти ошибки могут завершить конвейер выполнения. Ошибки, записанные в этот поток, также добавляются в `$Error` автоматическую переменную. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

## <a name="warning-stream"></a>Поток предупреждений

Поток **предупреждений** предназначен для состояний ошибки, которые менее серьезны, чем ошибки, записанные в поток **ошибок** . В нормальных условиях эти предупреждения не завершают выполнение. Предупреждения не записываются в `$Error` автоматическую переменную. Используйте `Write-Warning` командлет для явной записи в этот поток.

## <a name="verbose-stream"></a>Подробный поток

**Подробный** поток предназначен для сообщений, помогающих пользователям устранять неполадки в работе команды в интерактивном режиме или сценарии. Используйте `Write-Verbose` командлет для явного записи сообщений в этот поток. Многие командлеты предоставляют подробные выходные данные, которые полезны для понимания внутренних операций командлета. Подробные сообщения выводятся только при использовании `-Verbose` общего параметра. См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).

## <a name="debug-stream"></a>Поток отладки

Поток **отладки** используется для сообщений, которые помогают скриптам понять причину сбоя в коде. Используйте `Write-Debug` командлет для явной записи в этот поток. Сообщения отладки выводятся только при использовании `-Debug` общего параметра. См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).

Отладочные сообщения предназначены для разработчиков скриптов и командлетов, чем конечные пользователи. Эти отладочные сообщения могут содержать внутренние сведения, необходимые для глубокого устранения неполадок.

## <a name="information-stream"></a>Информационный поток

**Информационный** поток предназначен для предоставления сообщения, помогающего пользователю понять, что делает сценарий. Он также может использоваться разработчиками в качестве дополнительного потока, используемого для передачи информации с помощью PowerShell. Разработчик может пометить потоковые данные и иметь определенную обработку для этого потока. Используйте `Write-Information` командлет для явной записи в этот поток.

## <a name="progress-stream"></a>Поток хода выполнения

Поток **хода выполнения** используется для сообщений, которые сообщают о ходе выполнения команд и скриптов дольше. Используйте `Write-Progress` командлет для явного записи сообщений в этот поток. Поток **хода выполнения** не поддерживает перенаправление.

## <a name="see-also"></a>См. также статью

- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Ошибка записи](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [about_CommonParameters](about_CommonParameters.md)
- [about_Redirection](about_Redirection.md)
