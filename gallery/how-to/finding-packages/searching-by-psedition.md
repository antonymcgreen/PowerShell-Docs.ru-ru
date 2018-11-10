---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Пакеты с совместимыми выпусками PowerShell
ms.openlocfilehash: e16cfb0ee30e344c9399bec2985baafc5a252fd7
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003899"
---
# <a name="packages-with-compatible-powershell-editions"></a>Пакеты с совместимыми выпусками PowerShell

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

- **Выпуск Desktop Edition:** построен на основе .NET Framework и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в полноценных выпусках Windows, таких как Server Core и Windows Desktop.
- **Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-packages-compatible-for-specific-powershell-editions"></a>Коллекция PowerShell извлекает поддерживаемые метаданные PSEditions и позволяет отфильтровывать пакеты, совместимые с конкретными выпусками PowerShell

Если пакет имеет указанные совместимые версии PSEdition, они будут перечислены в разделе "Выпуски PowerShell" на странице отображения пакета, а также в результатах пакетов.

![Страница отображения элемента с выпусками PSEdition](../../Images/manual_package_download.png)

## <a name="search-for-packages-in-the-gallery-ui-which-works-on-powershellcore"></a>Поиск пакетов в коллекции пользовательского интерфейса, работающих в PowerShellCore

Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".

![Результаты поиска элементов, совместимых с Core PSEdition](../../Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".

![Результаты поиска элементов, совместимых с Desktop PSEdition](../../Images/SearchResultsWithPSEdition-Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a>Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell

- [Модули с PSEditions](../../concepts/module-psedition-support.md)
- [Скрипты с PSEdition](../../concepts/script-psedition-support.md)
