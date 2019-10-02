---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: коллекции,powershell,командлет,psgallery
title: Пакеты с совместимыми выпусками PowerShell или операционных систем
ms.openlocfilehash: 14038aa9b0453e1d06e6587e97da391b56297c75
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328445"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a>Пакеты с совместимыми выпусками PowerShell или операционных систем

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

## <a name="searching-by-powershell-edition"></a>Поиск по выпуску PowerShell

Есть два выпуска PowerShell:
- **Desktop Edition:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.
- **Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a>Коллекция PowerShell позволяет фильтровать пакеты, совместимые с конкретными выпусками PowerShell.

Если пакет имеет указанные совместимые версии PSEdition, они будут перечислены в разделе "Выпуски PowerShell" на странице отображения пакета, а также в результатах среди пакетов.
Кроме того, можно вести поиск совместимых пакетов с помощью PowerShell.

![Страница отображения элемента с выпусками PSEdition](../../Images/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a>Поиск пакетов в коллекции пользовательского интерфейса, работающих в PowerShellCore

Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".

### <a name="use-tagspsedition_core-to-search-items-compatible-with-powershell-core-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".

![Результаты поиска элементов, совместимых с Core PSEdition](../../Images/searchresultswithpseditions.PNG)

### <a name="use-tagspsedition_desktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".

![Результаты поиска элементов, совместимых с Desktop PSEdition](../../Images/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a>Поиск совместимых выпусков среди пакетов с помощью PowerShell
Можно указать теги для фильтрации выпуска PowerShell и операционной системы.
Используйте командлет `Find-Package` с параметром `-Tag`, чтобы указать выпуск (и ОС), который вы используете.
Пример:

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a>Поиск по операционной системе

Так как выпуск PowerShell Core доступен для Windows, Linux и MacOS, пакеты в коллекции могут быть предназначены для любого сочетания этих операционных систем. В пользовательском интерфейсе коллекции с помощью следующих тегов поиска можно найти пакеты для конкретной операционной системы:

- Теги: "Windows"
- Теги: "Linux"
- Теги: "MacOS"

Эти теги можно указать в `Find-Module` (и других командлетах из модуля PowerShellGet) следующим образом:

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a>Поиск нескольких совместимостей

Можно найти пакет, который содержит несколько совместимостей, с помощью такого синтаксиса:

Теги: "Совместимость1" "Совместимость2"

Например, если вы ищете пакет, совместимый с PowerShell Core на компьютерах с Windows и Linux, используйте следующие теги поиска:

Теги: "PSEdition_Core" "Windows" "Linux"

Чтобы выполнить поиск с помощью PowerShell, можно использовать `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:

```powershell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a>Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell

- [Модули с PSEditions](../../concepts/module-psedition-support.md)
- [Скрипты с PSEdition](../../concepts/script-psedition-support.md)
