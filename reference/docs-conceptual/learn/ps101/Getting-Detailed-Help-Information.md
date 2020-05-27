---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Получение подробной справки
ms.openlocfilehash: e722eb8a0ca13e3d2de864314775a0a9fa578390
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808500"
---
# <a name="getting-detailed-help-information"></a>Получение подробной справки

PowerShell содержит подробные статьи справки, объясняющие концепции и язык PowerShell. Статьи предоставляют сведения о каждом командлете и поставщике, а также многих функциях и скриптах.

Эти статьи можно отобразить в интерфейсе командной строки или просмотреть их последние обновленные версии в онлайн-документации по [PowerShell](/powershell/scripting/overview).

## <a name="getting-help-for-cmdlets"></a>Получение справки по командлетам

Для получения справки по командлетам PowerShell используйте командлет [Get-Help](/powershell/module/microsoft.powershell.core/Get-Help). Например, для получения справки по командлету `Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem
```

или диспетчер конфигурации служб

```powershell
Get-ChildItem -?
```

Справку можно получить и по самому командлету Get-Help. Пример:

```powershell
Get-Help Get-Help
```

Чтобы отобразить список всех статей справки о командлетах в рамках текущего сеанса, введите следующее:

```powershell
Get-Help -Category Cmdlet
```

Чтобы отобразить каждую статью справки постранично, используйте функцию `help` или ее псевдоним `man`.
Например, чтобы отобразить справку по командлету `Get-ChildItem`, введите следующее:

```powershell
man Get-ChildItem
```

или диспетчер конфигурации служб

```powershell
help Get-ChildItem
```

Чтобы отобразить подробную информацию, используйте параметр **Detailed** командлета `Get-Help`. Например, чтобы получить подробные сведения о командлете `Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem -Detailed
```

Чтобы отобразить все содержимое статьи справки, используйте параметр **Full** командлета `Get-Help`. Например, чтобы отобразить все содержимое статьи справки о командлете `Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem -Full
```

Чтобы получить подробную справку по параметрам командлета, используйте параметр **Parameter** командлета `Get-Help`. Например, чтобы получить подробную справку по всем параметрам командлета`Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem -Parameter *
```

Чтобы отобразить только примеры из статьи справки, используйте параметр **Examples** командлета `Get-Help`.
Например, чтобы вывести только примеры из статьи справки о командлете `Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem -Examples
```

Сведения о написании статей справки о командлетах см. в руководстве по [написанию справки по командлетам](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

## <a name="getting-conceptual-help"></a>Получение справки по концепциям

Командлет `Get-Help` также можно использовать для отображения статей справки по концепциям PowerShell, в том числе статей о языке PowerShell. Посвященные концепциям статьи справки начинаются с префикса about_, например about_line_editing. (Название статьи о концепциях нужно вводить на английском языке, даже если используется локализованная версия PowerShell.)

Для отображения списка статей о концепциях введите следующее:

```powershell
Get-Help about_*
```

Для отображения определенной статьи справки введите название этой статьи, например:

```powershell
Get-Help about_command_syntax
```

Параметры командлета `Get-Help`, например **Detailed**, **Parameter** и **Examples**, не влияют на отображение статей справки о концепциях.

## <a name="getting-help-about-providers"></a>Получение справки по поставщикам

Командлет `Get-Help` позволяет получить информацию о поставщиках PowerShell. Чтобы получить справку по поставщику, введите команду `Get-Help` и имя поставщика. Например, чтобы получить справку для поставщика Registry, введите:

```powershell
Get-Help registry
```

Чтобы отобразить список всех статей справки о поставщиках для текущего сеанса, введите следующее:

```powershell
Get-Help -Category provider
```

Параметры командлета `Get-Help`, например **Detailed**, **Parameter** и **Examples**, не влияют на отображение статей справки о поставщиках.

## <a name="getting-help-about-scripts-and-functions"></a>Получение справки по скриптам и функциям

Многим скриптам и функциям PowerShell посвящены отдельные статьи справки. Используйте командлет `Get-Help`, чтобы отобразить статьи справки о скриптах и функциях.

Чтобы получить справку по определенной функции, введите команду `Get-Help` и имя этой функции. Например, чтобы получить справку по функции `Disable-PSRemoting`, введите следующее:

```powershell
Get-Help Disable-PSRemoting
```

Чтобы получить справку по определенному скрипту, введите путь к файлу этого скрипта. Если путь к скрипту не указан в переменной среды Path, необходимо указать полный путь.

Например, если скрипт TestScript.ps1 находится в каталоге C:\\PS-Test, чтобы отобразить статью справки об этом скрипте, введите следующее:

```powershell
Get-Help c:\ps-test\TestScript.ps1
```

Параметры отображения справки по командлетам также позволяют отображать справку по скриптам и функциям. Справка по функциям и скриптам не выводится, если задана команда `Get-Help *`.

См. дополнительные сведения о написании статей справки о функциях и скриптах:

- [about_Functions](/powershell/module/microsoft.powershell.core/about/about_functions)
- [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)

## <a name="getting-help-online"></a>Получение справки в Интернете

Лучше всего использовать интернет-версии статей справки. Статьи в Интернете легко обновлять, поэтому в них содержится самая актуальная информация.

Чтобы отобразить интернет-версию статьи справки используйте параметр **Online** командлета `Get-Help`. Все статьи справки, содержащиеся в PowerShell, в том числе статьи справки о поставщиках и концепциях (About), можно найти в онлайн-документации по [PowerShell](/powershell/scripting/powershell-scripting).

> [!NOTE]
> Параметр **Online** нельзя использовать для отображения статей справки о концепциях (about_\*) и поставщиках.
> Статьи справки об отдельных командлетах, функциях и скриптах могут не иметь интернет-версий.

Например, чтобы открыть интернет-версию статьи справки о командлете `Get-ChildItem`, введите следующее:

```powershell
Get-Help Get-ChildItem -Online
```

PowerShell откроет статью в вашем браузере по умолчанию. Если статья справки имеет интернет-версию, можно также узнать ее URL-адрес. URL-адрес отображается в разделе со связанными ссылками в статье справки.

Например, чтобы посмотреть адрес интернет-версии командлета Add-Computer, введите следующее:

```powershell
Get-Help Add-Computer
```

Первая строка в разделе со связанными ссылками в статье показана ниже.

```Output
Online version: https://go.microsoft.com/fwlink/?LinkId=821564
```

Сведения об обеспечении интернет-поддержки собственных статей справки см. в разделе [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).

## <a name="see-also"></a>См. также раздел

- [about_Functions](/powershell/module/microsoft.powershell.core/about/about_functions)
- [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)
- [Get-Help](/powershell/module/microsoft.powershell.core/get-help)
