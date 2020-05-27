---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: коллекции,powershell,командлет,psgallery
title: Пакеты с совместимыми выпусками PowerShell или операционных систем
ms.openlocfilehash: fce1383fa604a555a40b050ce92c5cc45ca7054c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83691454"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a><span data-ttu-id="bbe05-103">Пакеты с совместимыми выпусками PowerShell или операционных систем</span><span class="sxs-lookup"><span data-stu-id="bbe05-103">Packages with compatible PowerShell Editions or Operating Systems</span></span>

<span data-ttu-id="bbe05-104">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="bbe05-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibilities.</span></span>

## <a name="searching-by-powershell-edition"></a><span data-ttu-id="bbe05-105">Поиск по выпуску PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbe05-105">Searching by PowerShell Edition</span></span>

<span data-ttu-id="bbe05-106">Есть два выпуска PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbe05-106">The two editions of PowerShell are:</span></span>

- <span data-ttu-id="bbe05-107">**Desktop Edition:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="bbe05-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="bbe05-108">**Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="bbe05-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="bbe05-109">Коллекция PowerShell позволяет фильтровать пакеты, совместимые с конкретными выпусками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbe05-109">PowerShell Gallery allows you to filter packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="bbe05-110">Если пакет имеет указанные совместимые версии PSEdition, они будут перечислены в разделе "Выпуски PowerShell" на странице отображения пакета, а также в результатах среди пакетов.</span><span class="sxs-lookup"><span data-stu-id="bbe05-110">If a package has compatible PSEditions specified, they are listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>
<span data-ttu-id="bbe05-111">Кроме того, можно вести поиск совместимых пакетов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbe05-111">You can also search for compatible packages using PowerShell.</span></span>

![Страница отображения элемента с выпусками PSEdition](media/searching-by-compatibility/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a><span data-ttu-id="bbe05-113">Поиск пакетов в коллекции пользовательского интерфейса, работающих в PowerShellCore</span><span class="sxs-lookup"><span data-stu-id="bbe05-113">Search for packages in the gallery UI that work on PowerShell Core</span></span>

<span data-ttu-id="bbe05-114">Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="bbe05-114">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspsedition_core-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="bbe05-115">Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="bbe05-115">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>

![Результаты поиска элементов, совместимых с Core PSEdition](media/searching-by-compatibility/searchresultswithpseditions.PNG)

### <a name="use-tagspsedition_desktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="bbe05-117">Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".</span><span class="sxs-lookup"><span data-stu-id="bbe05-117">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>

![Результаты поиска элементов, совместимых с Desktop PSEdition](media/searching-by-compatibility/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a><span data-ttu-id="bbe05-119">Поиск совместимых выпусков среди пакетов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbe05-119">Search for packages to find compatible editions using PowerShell</span></span>
<span data-ttu-id="bbe05-120">Можно указать теги для фильтрации выпуска PowerShell и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bbe05-120">You can specify tags to filter for the PowerShell edition and OS.</span></span>
<span data-ttu-id="bbe05-121">Используйте командлет `Find-Package` с параметром `-Tag`, чтобы указать выпуск (и ОС), который вы используете.</span><span class="sxs-lookup"><span data-stu-id="bbe05-121">You use the `Find-Package` cmdlet specifying the `-Tag` parameter to specify the edition (and OS) you are targeting.</span></span>
<span data-ttu-id="bbe05-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="bbe05-122">Like this:</span></span>

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a><span data-ttu-id="bbe05-123">Поиск по операционной системе</span><span class="sxs-lookup"><span data-stu-id="bbe05-123">Searching by Operating System</span></span>

<span data-ttu-id="bbe05-124">Так как выпуск PowerShell Core доступен для Windows, Linux и MacOS, пакеты в коллекции могут быть предназначены для любого сочетания этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="bbe05-124">Since PowerShell Core is available for Windows, Linux, and MacOS, packages in the Gallery may be designed for any combination of these operating systems.</span></span> <span data-ttu-id="bbe05-125">В пользовательском интерфейсе коллекции с помощью следующих тегов поиска можно найти пакеты для конкретной операционной системы:</span><span class="sxs-lookup"><span data-stu-id="bbe05-125">In the gallery UI use the following searchs tags to find packages tagged by operating system:</span></span>

- <span data-ttu-id="bbe05-126">Теги: "Windows"</span><span class="sxs-lookup"><span data-stu-id="bbe05-126">Tags: "Windows"</span></span>
- <span data-ttu-id="bbe05-127">Теги: "Linux"</span><span class="sxs-lookup"><span data-stu-id="bbe05-127">Tags: "Linux"</span></span>
- <span data-ttu-id="bbe05-128">Теги: "MacOS"</span><span class="sxs-lookup"><span data-stu-id="bbe05-128">Tags: "MacOS"</span></span>

<span data-ttu-id="bbe05-129">Эти теги можно указать в `Find-Module` (и других командлетах из модуля PowerShellGet) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbe05-129">You can specify these tags on `Find-Module` (and other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a><span data-ttu-id="bbe05-130">Поиск нескольких совместимостей</span><span class="sxs-lookup"><span data-stu-id="bbe05-130">Searching for Multiple Compatibilities</span></span>

<span data-ttu-id="bbe05-131">Можно найти пакет, который содержит несколько совместимостей, с помощью такого синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="bbe05-131">You can look for a package that has multiple compatibilities by using the syntax:</span></span>

<span data-ttu-id="bbe05-132">Теги: "Совместимость1" "Совместимость2"</span><span class="sxs-lookup"><span data-stu-id="bbe05-132">Tags: "Compatibility1" "Compatibility2"</span></span>

<span data-ttu-id="bbe05-133">Например, если вы ищете пакет, совместимый с PowerShell Core на компьютерах с Windows и Linux, используйте следующие теги поиска:</span><span class="sxs-lookup"><span data-stu-id="bbe05-133">For example, if you are looking for a package with PowerShell Core Compatibility that runs on both my Windows and Linux machines, use the search tags:</span></span>

<span data-ttu-id="bbe05-134">Теги: "PSEdition_Core" "Windows" "Linux"</span><span class="sxs-lookup"><span data-stu-id="bbe05-134">Tags: "PSEdition_Core" "Windows" "Linux"</span></span>

<span data-ttu-id="bbe05-135">Чтобы выполнить поиск с помощью PowerShell, можно использовать `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbe05-135">To search using PowerShell, you can use the `Find-Module` (and the other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="bbe05-136">Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbe05-136">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="bbe05-137">Модули с PSEditions</span><span class="sxs-lookup"><span data-stu-id="bbe05-137">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="bbe05-138">Сценарии с PSEditions</span><span class="sxs-lookup"><span data-stu-id="bbe05-138">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
