---
description: Описывает оснастки Windows PowerShell и показывает, как использовать их и управлять ими.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: cc22f8de0b9d8a55dcfa12f3b47f3852d891e67b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231997"
---
# <a name="about-pssnapins"></a>О PSSnapin

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описывает оснастки Windows PowerShell и показывает, как использовать их и управлять ими.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Оснастка Windows PowerShell — это сборка Microsoft .NET Framework, которая содержит поставщики и \/ командлеты Windows PowerShell. Windows PowerShell включает набор основных оснасток, но вы можете расширить возможности и преимущества Windows PowerShell, добавив оснастки, которые содержат поставщики и командлеты, созданные или получаемые из других.

При добавлении оснастки командлеты и поставщики, которые она содержит, немедленно становятся доступными для использования в текущем сеансе, но это изменение затрагивает только текущий сеанс.

Чтобы добавить оснастку во все будущие сеансы, сохраните ее в профиле Windows PowerShell. Можно также использовать командлет Export-Console, чтобы сохранить имена оснасток в файле консоли, а затем использовать их в будущих сеансах. Можно даже сохранить несколько консольных файлов, каждый из которых имеет другой набор оснасток.

Примечание. оснастки Windows PowerShell (PSSnapin) доступны для использования в Windows PowerShell 3,0 и Windows PowerShell 2,0. Они могут быть изменены или недоступны в последующих версиях. Для упаковки командлетов и поставщиков Windows PowerShell используйте модули. Сведения о создании модулей и преобразовании оснасток в модули см. в разделе [написание модуля Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

### <a name="finding-snap-ins"></a>ПОИСК ОСНАСТОК

Чтобы получить список оснасток Windows PowerShell на компьютере, введите:

```powershell
Get-PSSnapin
```

Чтобы получить оснастку для каждого поставщика Windows PowerShell, введите:

```powershell
Get-PSProvider | Format-List name, pssnapin
```

Чтобы получить список командлетов в оснастке Windows PowerShell, введите:

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a>УСТАНОВКА ОСНАСТКИ

Встроенные оснастки регистрируются в системе и добавляются в сеанс по умолчанию при запуске Windows PowerShell. Однако необходимо зарегистрировать оснастки, созданные или получаемые от других, а затем добавить оснастки в сеанс.

### <a name="registering-a-snap-in"></a>РЕГИСТРАЦИЯ ОСНАСТКИ

Оснастка Windows PowerShell — это программа, написанная на языке .NET Framework, который компилируется в DLL-файл. Чтобы использовать поставщики и командлеты в оснастке, необходимо сначала зарегистрировать оснастку (добавить ее в реестр).

В большинство оснасток входит программа установки (exe-или MSI-файл), которая регистрирует файл. dll. Однако если вы получаете оснастку в виде DLL-файла, вы можете зарегистрировать ее в системе. Дополнительные сведения см. в разделе [Регистрация командлетов, поставщиков и ведущих приложений](https://go.microsoft.com/fwlink/?LinkID=143619) в библиотеке MSDN.

Чтобы получить все зарегистрированные оснастки в системе или убедиться, что оснастка зарегистрирована, введите:

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a>ДОБАВЛЕНИЕ ОСНАСТКИ В ТЕКУЩИЙ СЕАНС

Чтобы добавить зарегистрированную оснастку в текущий сеанс, используйте командлет Add-PsSnapin. Например, чтобы добавить в сеанс оснастку Microsoft SQL Server, введите:

```powershell
Add-PSSnapin sql
```

После завершения команды поставщики и командлеты в оснастке будут доступны в сеансе. Однако они доступны только в текущем сеансе, если они не сохранены.

### <a name="saving-the-snap-ins"></a>СОХРАНЕНИЕ ОСНАСТОК

Чтобы использовать оснастку в будущих сеансах Windows PowerShell, добавьте команду Add-PsSnapin в профиль Windows PowerShell. Также можно экспортировать имена оснасток в файл консоли.

Если добавить в профиль команду Add-PSSnapin, она будет доступна во всех будущих сеансах Windows PowerShell. Если вы экспортируете имена оснасток в сеансе, файл экспорта можно использовать только тогда, когда требуются оснастки.

Чтобы добавить команду Add-PsSnapin в профиль Windows PowerShell, откройте профиль, вставьте или введите команду, а затем сохраните профиль. Дополнительные сведения см. в разделе about_Profiles.

Чтобы сохранить оснастки из сеанса в файле консоли (. psc1), используйте командлет Export-Console. Например, чтобы сохранить оснастки в текущей конфигурации сеанса в файле Невконсоле. psc1 в текущем каталоге, введите:

```powershell
Export-Console NewConsole
```

Дополнительные сведения см. в разделе Export-Console.

### <a name="opening-windows-powershell-with-a-console-file"></a>ОТКРЫТИЕ WINDOWS POWERSHELL С ПОМОЩЬЮ ФАЙЛА КОНСОЛИ

Чтобы использовать файл консоли, включающий оснастку, запустите Windows PowerShell (PowerShell.exe) из командной строки в Cmd.exe или в другом сеансе Windows PowerShell. Используйте параметр PsConsoleFile, чтобы указать файл консоли, включающий оснастку. Например, следующая команда запускает Windows PowerShell с файлом консоли Невконсоле. psc1:

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

Поставщики и командлеты в оснастке теперь доступны для использования в сеансе.

### <a name="removing-a-snap-in"></a>УДАЛЕНИЕ ОСНАСТКИ

Чтобы удалить оснастку Windows PowerShell из текущего сеанса, используйте командлет Remove-PsSnapin. Например, чтобы удалить оснастку SQL Server из текущего сеанса, введите:

```powershell
Remove-PSSnapin sql
```

Этот командлет удаляет оснастку из сеанса. Оснастка все еще загружена, но поставщики и командлеты, которые она поддерживает, больше не доступны.

### <a name="built-in-commands"></a>ВСТРОЕННЫЕ КОМАНДЫ

В Windows PowerShell 2,0 и в старых программах Windows PowerShell 3,0 и более поздних версиях встроенные команды, устанавливаемые вместе с Windows PowerShell, упаковываются в оснастки, которые автоматически добавляются в каждый сеанс Windows PowerShell.

Начиная с Windows PowerShell 3,0, в более новых приложениях-компонентах, запускающих сеансы с помощью метода InitialSessionState. CreateDefault2 — встроенные команды упаковываются в модули. Исключением является Microsoft. PowerShell. Core, которое всегда отображается как оснастка. Основная оснастка по умолчанию включена в каждый сеанс. Встроенные модули загружаются автоматически при первом использовании.

Примечание. удаленные сеансы, включая сеансы, запущенные с помощью командлета New-PSSession, — это сеансы предыдущих версий, в которых встроенные команды упаковываются в оснастки.

Следующие оснастки (или модули) устанавливаются вместе с Windows PowerShell.

- Microsoft. PowerShell. Core — содержит поставщики и командлеты, используемые для управления основными функциями Windows PowerShell. Он включает в себя файл FileSystem, реестр, псевдоним, среду, функцию и поставщики переменных, а также базовые командлеты, такие как Get-Help, Get-Command и Get-History.

- Microsoft. PowerShell. host — содержит командлеты, используемые узлом Windows PowerShell, такие как Start-Transcript и командлеты типа "точка-расшифровка".

- Microsoft. PowerShell. Management — содержит командлеты, такие как Get-Service и Get-ChildItem, которые используются для управления компонентами Windows.

- Microsoft. PowerShell. Security — содержит поставщик сертификатов и командлеты, используемые для управления безопасностью Windows PowerShell, такие как Get-ACL, Get-AuthenticodeSignature и ConvertTo-SecureString.

- Microsoft. PowerShell. Utility — содержит командлеты, используемые для работы с объектами и данными, например Get-Member, Write-Host и Format-List.

- Microsoft. WSMan. Management — содержит поставщик WSMan и командлеты, управляющие службой служба удаленного управления Windows, такие как Connect-WSMan и Enable-WSManCredSSP.

## <a name="logging-snap-in-events"></a>РЕГИСТРАЦИЯ СОБЫТИЙ ОСНАСТКИ

Начиная с Windows PowerShell 3,0, вы можете записывать события выполнения для командлетов в модулях и оснастках Windows PowerShell, установив для свойства LogPipelineExecutionDetails модулей и оснасток значение TRUE. Дополнительные сведения см. в разделе [about_EventLogs](about_EventLogs.md).

## <a name="see-also"></a>СМ. ТАКЖЕ

[Add-PsSnapin](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[Get-PsSnapin](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[Remove-PsSnapin](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[Export-Console](xref:Microsoft.PowerShell.Core.Export-Console)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[about_Profiles](about_Profiles.md)

[about_Modules](about_Modules.md)

## <a name="keywords"></a>СЛОВАМИ

about_Snapins, about_Snap_ins, about_Snap
