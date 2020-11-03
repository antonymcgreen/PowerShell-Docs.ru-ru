---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226726"
---
# Add-PSSnapin

## Краткий обзор
Добавляет в текущий сеанс одну или несколько оснасток Windows PowerShell.

## SYNTAX

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Add-PSSnapin`Командлет добавляет зарегистрированные оснастки Windows PowerShell в текущий сеанс. После добавления оснастки можно использовать в текущем сеансе командлеты и поставщиков, поддерживающих оснастки.

Чтобы добавить оснастку во все будущие сеансы Windows PowerShell, добавьте `Add-PSSnapin` команду в профиль Windows PowerShell. Дополнительные сведения см. в разделе [about_Profiles](about/about_Profiles.md).

Начиная с Windows PowerShell 3.0, основные команды, включенные в Windows PowerShell, упаковываются в модули. Исключение составляет **Microsoft.PowerShell.Core** , который является оснасткой (PSSnapin).
По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**. Модули импортируются автоматически при первом использовании. для их импорта можно использовать командлет Import-Module.

## Примеры

### Пример 1. Добавление оснасток

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

Эта команда добавляет оснастки Microsoft Exchange и Active Directory в текущий сеанс.

### Пример 2. Добавление всех зарегистрированных оснасток

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

Эта команда добавляет в сеанс все зарегистрированные оснастки Windows PowerShell. Для получения объектов, представляющих все зарегистрированные оснастки, используется командлет Get-PSSnapin с **зарегистрированным** параметром. Оператор конвейера (|) передает результат в `Add-PSSnapin` , который добавляет их в сеанс. Параметр **PassThru** возвращает объекты, представляющие все добавленные оснастки.

### Пример 3. Регистрация оснастки и добавление ее

Первая команда получает оснастки, которые были добавлены в текущий сеанс, включающий оснастки, которые устанавливаются вместе с Windows PowerShell. В этом примере ManagementFeatures не возвращается. Это означает, что данная оснастка в сеанс не добавлена.

Вторая команда получает оснастки, которые были зарегистрированы в системе, включая те, которые уже были добавлены в сеанс. В нее не входят оснастки, устанавливаемые вместе с Windows PowerShell. В этом случае команда не возвращает ни одной оснастки. Это означает, что оснастка Манажементфеатурес не зарегистрирована в системе.

Третья команда создает псевдоним, InstallUtil, для пути к средству InstallUtil в .NET Framework.

Четвертая команда использует средство InstallUtil для регистрации оснастки. Команда задает путь к ManagementCmdlets.dll, имя файла или модуля оснастки.

Пятая команда совпадает со второй, но на этот раз она используется для того, чтобы проверить регистрацию оснастки ManagementCmdlets.

Шестая команда использует `Add-PSSnapin` командлет для добавления к сеансу оснастки манажементфеатурес. Она указывает имя оснастки, ManagementFeatures, а не имя файла.

Чтобы убедиться, что оснастка добавлена в сеанс, Седьмая команда использует параметр **module** командлета Get-Command. Она отображает элементы, добавленные в сеанс оснасткой или модулем.

Можно также использовать свойство **PSSnapin** объекта, `Get-Command` возвращаемого командлетом, для поиска оснастки или модуля, в котором был создан командлет. Восьмая команда использует точечную нотацию для поиска значения свойства PSSnapin командлета Set-Alias.

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

В этом примере показан процесс регистрации оснастки в системе и последующее добавление этой оснастки в сеанс. В нем используется Манажементфеатурес — вымышленная оснастка, реализованная в файле с именем ManagementCmdlets.dll.

## PARAMETERS

### -Name

Задает имя оснастки. Это имя, а не AssemblyName или ModuleName. Разрешено использовать подстановочные знаки.

Чтобы найти имена зарегистрированных оснасток в системе, введите `Get-PSSnapin -Registered` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Указывает, что этот командлет возвращает объект, представляющий каждую добавленную оснастку. По умолчанию этот командлет не создает выходные данные.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### None или System. Management. Automation. PSSnapInInfo

Этот командлет возвращает объект PSSnapInInfo, представляющий оснастку, если указан параметр **PassThru** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Начиная с Windows PowerShell 3.0, основные команды, включенные в Windows PowerShell, упаковываются в модули. В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях Windows PowerShell, основные команды упаковываются в оснастки (PSSnapin). Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой. Кроме того, удаленные сеансы, например, запущенные командлетом New-PSSession, являются сеансами предыдущих версий, включающими основные оснастки.

  Дополнительные сведения о методе **CreateDefault2** , который создает сеансы более новых версий с основными модулями, см. в разделе [метод CREATEDEFAULT2](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) в библиотеке MSDN.

* Дополнительные сведения об оснастках см. в разделе [about_PSSnapins](About/about_PSSnapins.md) и [Создание оснастки Windows PowerShell](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).
* `Add-PSSnapin` добавляет оснастку только в текущий сеанс. Чтобы оснастка добавлялась во все сеансы Windows PowerShell, вставьте эту команду в профиль Windows PowerShell. Дополнительные сведения см. в разделе about_Profiles.
* Можно добавить любую оснастку, зарегистрированную с помощью служебной программы установки Microsoft .NET Framework. Дополнительные сведения см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).
* Чтобы получить список оснасток, зарегистрированных на компьютере, введите `Get-PSSnapin -Registered` .
* Перед добавлением оснастки `Add-PSSnapin` проверяет версию оснастки, чтобы убедиться, что она совместима с текущей версией Windows PowerShell. Если оснастка не проходит проверку версии, Windows PowerShell сообщает об ошибке.

## Связанные ссылки

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
