---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: коллекции,powershell,командлет,psgallery
title: Пакеты с совместимыми выпусками PowerShell или операционной системы
ms.openlocfilehash: 8230866561d3021379a48cc2c83fb4104a4058c1
ms.sourcegitcommit: d396d0e4cfe3d279f399c17e7337380a31d373ac
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2018
ms.locfileid: "53747710"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a><span data-ttu-id="0dfde-103">Пакеты с совместимыми выпусками PowerShell или операционных систем</span><span class="sxs-lookup"><span data-stu-id="0dfde-103">Packages with compatible PowerShell Editions or Operating Systems</span></span>

<span data-ttu-id="0dfde-104">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="0dfde-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibilities.</span></span>

## <a name="searching-by-powershell-edition"></a><span data-ttu-id="0dfde-105">Поиск по выпуску PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dfde-105">Searching by PowerShell Edition</span></span> 
<span data-ttu-id="0dfde-106">В двух версиях Powershell являются:</span><span class="sxs-lookup"><span data-stu-id="0dfde-106">The two editions of Powershell are:</span></span>
- <span data-ttu-id="0dfde-107">Desktop Edition На платформе .NET Framework и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в полноценных выпусках Windows, такие как ядро сервера и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="0dfde-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="0dfde-108">**Выпуск Core:** Опирается на .NET Core и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в сокращенных выпусках Windows, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="0dfde-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="0dfde-109">Коллекция PowerShell позволяет фильтровать пакеты совместимы конкретными выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dfde-109">PowerShell Gallery allows you to filter packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="0dfde-110">Если пакет содержит совместимых PSEditions указаны, они перечислены как часть «Выпуски PowerShell» в отображаемой страницы пакета, а также в результатах пакетов.</span><span class="sxs-lookup"><span data-stu-id="0dfde-110">If a package has compatible PSEditions specified, they are listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>
<span data-ttu-id="0dfde-111">Кроме того, можно выполнять поиск совместимых пакетов, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dfde-111">You can also search for compatible packages using PowerShell.</span></span>

![Страница отображения элемента с выпусками PSEdition](../../Images/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a><span data-ttu-id="0dfde-113">Поиск пакетов в коллекции пользовательского интерфейса, которые работают в PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="0dfde-113">Search for packages in the gallery UI that work on PowerShell Core</span></span>

<span data-ttu-id="0dfde-114">Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="0dfde-114">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="0dfde-115">Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".</span><span class="sxs-lookup"><span data-stu-id="0dfde-115">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>

![Результаты поиска элементов, совместимых с Core PSEdition](../../Images/searchresultswithpseditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="0dfde-117">Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".</span><span class="sxs-lookup"><span data-stu-id="0dfde-117">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>

![Результаты поиска элементов, совместимых с Desktop PSEdition](../../Images/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a><span data-ttu-id="0dfde-119">Поиск пакетов найти совместимыми выпусками с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dfde-119">Search for packages to find compatible editions using PowerShell</span></span>
<span data-ttu-id="0dfde-120">Можно указать теги для фильтрации версии PowerShell и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="0dfde-120">You can specify tags to filter for the PowerShell edition and OS.</span></span> <span data-ttu-id="0dfde-121">Использовании `Find-Package` указание командлет `-Tag` параметр, чтобы указать выпуск (и ОС) вы используете.</span><span class="sxs-lookup"><span data-stu-id="0dfde-121">You use the `Find-Package` cmdlet specifying the `-Tag` parameter to specify the edition (and OS) you are targeting.</span></span>
<span data-ttu-id="0dfde-122">Типа того:</span><span class="sxs-lookup"><span data-stu-id="0dfde-122">Like this:</span></span>

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a><span data-ttu-id="0dfde-123">Поиск по операционной системы</span><span class="sxs-lookup"><span data-stu-id="0dfde-123">Searching by Operating System</span></span> 

<span data-ttu-id="0dfde-124">Так как PowerShell Core будет доступен для Windows, Linux и MacOS, пакеты в коллекции может обеспечивать любое сочетание этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="0dfde-124">Since PowerShell Core is available for Windows, Linux, and MacOS, packages in the Gallery may be designed for any combination of these operating systems.</span></span> <span data-ttu-id="0dfde-125">В коллекции пользовательского интерфейса с помощью следующих тегов searchs для поиска пакетов, отмеченному поведением операционной системы:</span><span class="sxs-lookup"><span data-stu-id="0dfde-125">In the gallery UI use the following searchs tags to find packages tagged by operating system:</span></span>

- <span data-ttu-id="0dfde-126">Теги: "Windows"</span><span class="sxs-lookup"><span data-stu-id="0dfde-126">Tags: "Windows"</span></span>
- <span data-ttu-id="0dfde-127">Теги: "Linux"</span><span class="sxs-lookup"><span data-stu-id="0dfde-127">Tags: "Linux"</span></span>
- <span data-ttu-id="0dfde-128">Теги: "MacOS"</span><span class="sxs-lookup"><span data-stu-id="0dfde-128">Tags: "MacOS"</span></span> 

<span data-ttu-id="0dfde-129">Эти теги можно указать на `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0dfde-129">You can specify these tags on `Find-Module` (and other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a><span data-ttu-id="0dfde-130">Поиск нескольких совместимости</span><span class="sxs-lookup"><span data-stu-id="0dfde-130">Searching for Multiple Compatibilities</span></span>

<span data-ttu-id="0dfde-131">Можно найти пакет, который содержит несколько совместимости с помощью синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="0dfde-131">You can look for a package that has multiple compatibilities by using the syntax:</span></span> 

<span data-ttu-id="0dfde-132">Теги «Compatibility1» «Compatibility2»</span><span class="sxs-lookup"><span data-stu-id="0dfde-132">Tags: "Compatibility1" "Compatibility2"</span></span> 

<span data-ttu-id="0dfde-133">Например если вы ищете пакет с PowerShell Core совместимости, работающей на компьютерах моей Windows и Linux, используйте поиск тегов:</span><span class="sxs-lookup"><span data-stu-id="0dfde-133">For example, if you are looking for a package with PowerShell Core Compatibility that runs on both my Windows and Linux machines, use the search tags:</span></span>

<span data-ttu-id="0dfde-134">Теги «PSEdition_Core», «Windows», «Linux»</span><span class="sxs-lookup"><span data-stu-id="0dfde-134">Tags: "PSEdition_Core" "Windows" "Linux"</span></span> 

<span data-ttu-id="0dfde-135">Чтобы выполнить поиск с помощью PowerShell, можно использовать `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0dfde-135">To search using PowerShell, you can use the `Find-Module` (and the other cmdlets in the PowerShellGet module), like this:</span></span>

```powewrshell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="0dfde-136">Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dfde-136">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="0dfde-137">Модули с PSEditions</span><span class="sxs-lookup"><span data-stu-id="0dfde-137">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="0dfde-138">Скрипты с PSEdition</span><span class="sxs-lookup"><span data-stu-id="0dfde-138">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
