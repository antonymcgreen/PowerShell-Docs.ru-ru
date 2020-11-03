---
description: Описание ограничений Windows PowerShell 4,0 в Windows RT 8,1.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231882"
---
# <a name="about-windows-rt"></a>О Windows RT

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описание ограничений Windows PowerShell 4,0 в Windows RT 8,1.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Операционная система Windows RT 8,1 устанавливается на компьютерах и устройствах (например, на Microsoft Surface 2, на которых установлена операционная система, входящая в состав компьютера), использующих процессоры Advanced RISC Computer (ARM).

Windows PowerShell 4,0 входит в комплект Windows RT 8,1. Все командлеты, поставщики и модули, а большинство скриптов, предназначенных для Windows PowerShell 2,0 и более поздних версий, выполняются в Windows RT 8,1 без изменений.

Поскольку Windows RT 8,1 не включает все компоненты Windows, некоторые функции Windows PowerShell работают по-разному или не работают на устройствах под управлением Windows RT. Различия описаны в следующем списке.

- Интегрированная среда сценариев Windows PowerShell не включена в и не может работать в Windows RT 8,1.
  Интегрированная среда сценариев Windows PowerShell требует Windows Presentation Foundation, который не входит в Windows RT 8,1.

- Удаленное взаимодействие Windows PowerShell и служба WinRM по умолчанию отключены.
  Чтобы включить удаленное взаимодействие, выполните командлет Enable-PSRemoting. Кроме того, выполните командлет Set-Service, чтобы задать автоматический или автоматический режим запуска службы WinRM (отложенный запуск).

  Хотя удаленное взаимодействие отключено, можно использовать удаленное взаимодействие Windows PowerShell для выполнения команд на других компьютерах, но другие компьютеры не могут выполнять команды на устройстве Windows RT. Кроме того, неявное удаленное взаимодействие — это удаленное взаимодействие, встроенное в командлет или сценарий, которое не запрашивается явным образом с добавленными параметрами.
  - не работает в Windows PowerShell, работающем в Windows RT 8,1.

- В Windows RT 8,1 не поддерживаются присоединенные к домену вычисления и проверка подлинности Kerberos. Windows PowerShell нельзя использовать для добавления этих функций или управления ими.

- Классы Microsoft .NET Framework, которые не поддерживаются в Windows RT 8,1, также не поддерживаются Windows PowerShell в Windows RT 8,1.

- Транзакции не включены в Windows RT 8,1. Командлеты транзакций, такие как Start-Transaction и параметры транзакции, такие как UseTransaction, не работают должным образом.

- Все сеансы Windows PowerShell на устройствах Windows RT 8,1 используют языковой режим ConstrainedLanguage. Языковой режим ConstrainedLanguage является вспомогательным для целостности кода пользовательского режима (УМЦИ). Он позволяет использовать все командлеты Windows и языковые элементы Windows PowerShell, но запрещает использование Windows PowerShell для обхода или нарушения защиты УМЦИ.

Дополнительные сведения о языковом режиме ConstrainedLanguage см. в разделе [about_Language_Modes](about_Language_Modes.md).

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Language_Modes](about_Language_Modes.md)

[about_Remote](about_Remote.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)
