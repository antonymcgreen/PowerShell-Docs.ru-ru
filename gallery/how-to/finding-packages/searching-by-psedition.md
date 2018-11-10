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
# <a name="packages-with-compatible-powershell-editions"></a><span data-ttu-id="f5b90-103">Пакеты с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5b90-103">Packages with compatible PowerShell Editions</span></span>

<span data-ttu-id="f5b90-104">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="f5b90-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="f5b90-105">**Выпуск Desktop Edition:** построен на основе .NET Framework и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="f5b90-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="f5b90-106">**Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="f5b90-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="f5b90-107">Коллекция PowerShell извлекает поддерживаемые метаданные PSEditions и позволяет отфильтровывать пакеты, совместимые с конкретными выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5b90-107">PowerShell Gallery extracts supported PSEditions metadata and allows you to filters the packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="f5b90-108">Если пакет имеет указанные совместимые версии PSEdition, они будут перечислены в разделе "Выпуски PowerShell" на странице отображения пакета, а также в результатах пакетов.</span><span class="sxs-lookup"><span data-stu-id="f5b90-108">If a package has compatible PSEditions specified, they will be listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>

![Страница отображения элемента с выпусками PSEdition](../../Images/manual_package_download.png)

## <a name="search-for-packages-in-the-gallery-ui-which-works-on-powershellcore"></a><span data-ttu-id="f5b90-110">Поиск пакетов в коллекции пользовательского интерфейса, работающих в PowerShellCore</span><span class="sxs-lookup"><span data-stu-id="f5b90-110">Search for packages in the gallery UI which works on PowerShellCore</span></span>

<span data-ttu-id="f5b90-111">Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="f5b90-111">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="f5b90-112">Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="f5b90-112">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>

![Результаты поиска элементов, совместимых с Core PSEdition](../../Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="f5b90-114">Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".</span><span class="sxs-lookup"><span data-stu-id="f5b90-114">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>

![Результаты поиска элементов, совместимых с Desktop PSEdition](../../Images/SearchResultsWithPSEdition-Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="f5b90-116">Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5b90-116">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="f5b90-117">Модули с PSEditions</span><span class="sxs-lookup"><span data-stu-id="f5b90-117">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="f5b90-118">Скрипты с PSEdition</span><span class="sxs-lookup"><span data-stu-id="f5b90-118">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
