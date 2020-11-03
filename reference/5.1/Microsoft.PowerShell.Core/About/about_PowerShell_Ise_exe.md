---
description: Объясняется, как использовать средство командной строки PowerShell_Ise.exe.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232334"
---
# <a name="about-powershell-iseexe"></a>О Ise.exe PowerShell

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Объясняется, как использовать средство командной строки PowerShell_Ise.exe.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

PowerShell_Ise.exe запускает сеанс интегрированной среды сценариев (ISE) Windows PowerShell. Его можно запустить в Cmd.exe и в Windows PowerShell.

Чтобы запустить PowerShell_ISE.exe, введите PowerShell_ISE.exe, PowerShell_ISE или ISE.

## <a name="syntax"></a>SYNTAX

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a>PARAMETERS

### <a name="-file"></a>-File

Открывает указанные файлы в интегрированной среде сценариев Windows PowerShell. Имя параметра ("-File") является необязательным. Чтобы получить список из нескольких файлов, введите одну текстовую строку, заключенную в кавычки. Используйте запятые для разделения имен файлов в строке.

Пример:

PowerShell_ISE-файл "File1.ps1, File2.ps1, File3.xml".

В Windows PowerShell разрешены пробелы между именами файлов, но они могут неправильно интерпретироваться другими программами, например Cmd.exe.

Этот параметр можно использовать для открытия любого текстового файла, включая файлы сценариев Windows PowerShell и XML-файлы.

### <a name="-mta"></a>-Mta

Запускает интегрированную среду сценариев Windows PowerShell с использованием многопоточного подразделения. Этот параметр впервые появился в Windows PowerShell 3.0. Однопотоковое подразделение (STA) является значением по умолчанию.

### <a name="-noprofile"></a>-NoProfile

Не запускает профили Windows PowerShell. По умолчанию профили Windows PowerShell выполняются в каждом сеансе.

Этот параметр рекомендуется использовать при написании общего содержимого, например функций и скриптов, которые будут выполняться в системах с разными профилями.
Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).

### <a name="-help---"></a>-Help-?,/?

Отображает справку для PowerShell_ISE.exe.

## <a name="examples"></a>Примеры

Эти команды запускают интегрированную среду сценариев Windows PowerShell. Команды эквивалентны и взаимозаменяемы.

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

Эти команды открывают скрипт Get-Profile.ps1 в ИНТЕГРИРОВАНной среде сценариев Windows PowerShell.
Команды эквивалентны и взаимозаменяемы.

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

Эта команда открывает скрипты Get-Backups.ps1 и Get-BackupInstance.ps1 в интегрированной среде сценариев Windows PowerShell. Чтобы открыть более одного файла, используйте запятую для разделения имен файлов и заключите все значение имени файла в кавычки.

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

Эта команда запускает интегрированную среду сценариев Windows PowerShell без профилей.

```
PS C:> ISE -NoProfile
```

Эта команда возвращает справку для PowerShell_ISE.exe.

```
PS C:> ISE -help
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_PowerShell.exe](about_PowerShell_exe.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)

[Интегрированная среда сценариев (ISE) Windows PowerShell](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
