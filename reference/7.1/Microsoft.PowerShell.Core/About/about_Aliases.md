---
description: Описание использования альтернативных имен для командлетов и команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: e0a1fa357e591dd17986a8dd685a1818751ab355
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232706"
---
# <a name="about-aliases"></a>About Aliases (О псевдонимах)

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описание использования альтернативных имен для командлетов и команд в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Псевдоним — это альтернативное имя или псевдоним для командлета или для элемента Command, например функции, скрипта, файла или исполняемого файла. Вместо имени команды в командах PowerShell можно использовать псевдоним.

Чтобы создать псевдоним, используйте командлет New-Alias. Например, следующая команда создает псевдоним "газов" для `Get-AuthenticodeSignature` командлета:

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

После создания псевдонима для имени командлета можно использовать псевдоним вместо имени командлета. Например, чтобы получить подпись Authenticode для файла SqlScript.ps1, введите:

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

Или введите:

```powershell
gas SqlScript.ps1
```

При создании слова "Word" в качестве псевдонима для Microsoft Office Word можно ввести "Word" вместо следующего:

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a>ВСТРОЕННЫЕ ПСЕВДОНИМЫ

PowerShell включает набор встроенных псевдонимов, включая "CD" и "chdir" для командлета Set-Location, а также "ls" и "Dir" для командлета Get-ChildItem.

Чтобы получить все псевдонимы на компьютере, включая встроенные псевдонимы, введите:

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a>КОМАНДЛЕТЫ ALIAS

PowerShell включает следующие командлеты, предназначенные для работы с псевдонимами:

- `Get-Alias` — Получает все псевдонимы в текущем сеансе.
- `New-Alias` — Создает новый псевдоним.
- `Set-Alias` — Создает или изменяет псевдоним.
- `Export-Alias` — Экспортирует один или несколько псевдонимов в файл.
- `Import-Alias` — Импортирует файл псевдонима в PowerShell.

Для получения подробных сведений о командлетах введите:

```powershell
Get-Help <cmdlet-Name> -Detailed
```

Например, введите:

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a>СОЗДАНИЕ ПСЕВДОНИМА

Чтобы создать новый псевдоним, используйте командлет New-Alias. Например, чтобы создать псевдоним "GH" для Get-Help, введите:

```powershell
New-Alias -Name gh -Value Get-Help
```

Псевдоним можно использовать в командах так же, как и полное имя командлета, и можно использовать псевдоним с параметрами.

Например, чтобы получить подробную справку по командлету Get-WmiObject, введите:

```powershell
Get-Help Get-WmiObject -Detailed
```

Или введите:

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a>СОХРАНЕНИЕ ПСЕВДОНИМОВ

Создаваемые псевдонимы сохраняются только в текущем сеансе. Чтобы использовать псевдонимы в другом сеансе, добавьте псевдоним в профиль PowerShell. Или используйте командлет Export-Alias, чтобы сохранить псевдонимы в файл.

Чтобы получить дополнительные сведения, введите: 

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a>ПОЛУЧЕНИЕ ПСЕВДОНИМОВ

Чтобы получить все псевдонимы в текущем сеансе, включая встроенные псевдонимы, псевдонимы в профилях PowerShell и псевдонимы, созданные в текущем сеансе, введите:

```powershell
Get-Alias
```

Чтобы получить конкретные псевдонимы, используйте параметр Name командлета Get-Alias. Например, чтобы получить псевдонимы, начинающиеся с "p", введите:

```powershell
Get-Alias -Name p*
```

Чтобы получить псевдонимы для определенного элемента, используйте параметр определения. Например, чтобы получить псевдонимы для типа командлета Get-ChildItem:

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a>ПОЛУЧЕНИЕ ВЫХОДНОГО ПСЕВДОНИМА

Get-Alias возвращает только один тип объекта — объект AliasInfo (System. Management. Automation. AliasInfo). Имена псевдонимов, которые не содержат дефис, например "CD", отображаются в следующем формате:

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

Это позволяет быстро и легко получить необходимую информацию.

Формат имени псевдонима со стрелками не используется для псевдонимов, содержащих дефис. Они, скорее всего, являются предпочтительными заменяемыми именами для командлетов и функций, а не стандартных сокращений или псевдонимов, и автор может не потребовать от них очевидного.

## <a name="alternate-names-for-commands-with-parameters"></a>АЛЬТЕРНАТИВНЫЕ ИМЕНА ДЛЯ КОМАНД С ПАРАМЕТРАМИ

Можно назначить псевдоним командлету, сценарию, функции или исполняемому файлу. Нельзя назначить псевдоним для команды и ее параметров. Например, можно присвоить `Get-Eventlog` командлету псевдоним, но нельзя присвоить `Get-Eventlog -LogName System` команде псевдоним.

Можно создать функцию, которая включает команду. Чтобы создать функцию, введите слово "Function", за которым следует имя функции. Введите команду и заключите ее в фигурные скобки ( {} ).

Например, следующая команда создает функцию syslog. Эта функция представляет `Get-Eventlog -LogName System` команду:

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

Теперь можно ввести "syslog" вместо команды. И можно создавать псевдонимы для новой функции.

Для получения дополнительных сведений о функциях введите:

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a>ПСЕВДОНИМЫ ОБЪЕКТОВ

Псевдонимы PowerShell представлены объектами, которые являются экземплярами класса System. Management. Automation. AliasInfo. Дополнительные сведения об этом типе объектов см. в разделе [класс AliasInfo][aliasinfo] в библиотеке Microsoft Developer Network (MSDN).

Чтобы просмотреть свойства и методы объектов псевдонима, получите псевдонимы.
Затем передаем их в командлет Get-Member. Пример:

```powershell
Get-Alias | Get-Member
```

Чтобы просмотреть значения свойств определенного псевдонима, например `dir` псевдонима, получите псевдоним. Затем передаем его в командлет Format-List. Например, следующая команда возвращает псевдоним Dir. Затем команда передает псевдоним в командлет Format-List. Затем команда использует параметр Property объекта Format-List с подстановочным знаком ( \* ) для вывода всех свойств `dir` псевдонима. Следующая команда выполняет следующие задачи:

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a>Поставщик ПСЕВДОНИМов PowerShell

В PowerShell имеется поставщик псевдонимов. Поставщик псевдонимов позволяет просматривать псевдонимы в PowerShell, как будто они находятся на диске файловой системы.

Поставщик псевдонимов предоставляет диск Alias:. Чтобы войти в диск Alias:, введите:

```powershell
Set-Location Alias:
```

Чтобы просмотреть содержимое диска, введите:

```powershell
Get-ChildItem
```

Чтобы просмотреть содержимое диска с другого диска PowerShell, Начните путь с имени диска. Добавьте двоеточие (:). Пример:

```powershell
Get-ChildItem -Path Alias:
```

Чтобы получить сведения о конкретном псевдониме, введите имя диска и псевдоним. Или введите шаблон имени. Например, чтобы получить все псевдонимы, начинающиеся с "p", введите:

```powershell
Get-ChildItem -Path Alias:p*
```

Для получения дополнительных сведений о поставщике псевдонимов PowerShell введите:

```powershell
Get-Help Alias
```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [about_functions](about_functions.md)
- [about_profiles](about_profiles.md)
- [about_providers](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo

