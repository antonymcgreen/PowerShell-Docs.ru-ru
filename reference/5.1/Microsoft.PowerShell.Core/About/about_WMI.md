---
description: Инструментарий управления Windows (WMI) (WMI) использует модель CIM (CIM) для представления систем, приложений, сетей, устройств и других управляемых компонентов современного предприятия.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232269"
---
# <a name="about-wmi"></a><span data-ttu-id="573e3-104">Сведения об инструментарии WMI</span><span class="sxs-lookup"><span data-stu-id="573e3-104">About WMI</span></span>

## <a name="short-description"></a><span data-ttu-id="573e3-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="573e3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="573e3-106">Инструментарий управления Windows (WMI) (WMI) использует модель CIM (CIM) для представления систем, приложений, сетей, устройств и других управляемых компонентов современного предприятия.</span><span class="sxs-lookup"><span data-stu-id="573e3-106">Windows Management Instrumentation (WMI) uses the Common Information Model (CIM) to represent systems, applications, networks, devices, and other manageable components of the modern enterprise.</span></span>

## <a name="long-description"></a><span data-ttu-id="573e3-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="573e3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="573e3-108">Инструментарий управления Windows (WMI) (WMI) — это реализация корпорацией Майкрософт Web-Based Enterprise Management (WBEM), отраслевой стандарт.</span><span class="sxs-lookup"><span data-stu-id="573e3-108">Windows Management Instrumentation (WMI) is Microsoft's implementation of Web-Based Enterprise Management (WBEM), the industry standard.</span></span>

<span data-ttu-id="573e3-109">Классический Инструментарий WMI использует DCOM для взаимодействия с сетевыми устройствами для управления удаленными системами.</span><span class="sxs-lookup"><span data-stu-id="573e3-109">Classic WMI uses DCOM to communicate with networked devices to manage remote systems.</span></span> <span data-ttu-id="573e3-110">В Windows PowerShell 3,0 появилась модель поставщика CIM, использующая WinRM для удаления зависимости от DCOM.</span><span class="sxs-lookup"><span data-stu-id="573e3-110">Windows PowerShell 3.0 introduces a CIM provider model that uses WinRM to remove the dependency on DCOM.</span></span> <span data-ttu-id="573e3-111">Эта модель поставщика CIM также использует новые API-интерфейсы поставщика WMI, позволяющие разработчикам писать командлеты Windows PowerShell в машинном коде (C \+ \+ ).</span><span class="sxs-lookup"><span data-stu-id="573e3-111">This CIM provider model also uses new WMI provider APIs that enable developers to write Windows PowerShell cmdlets in native code (C\+\+).</span></span>

<span data-ttu-id="573e3-112">Не путайте поставщики WMI с поставщиками Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="573e3-112">Do not confuse WMI providers with Windows PowerShell providers.</span></span> <span data-ttu-id="573e3-113">Многие функции Windows имеют связанный поставщик WMI, предоставляющий возможности управления.</span><span class="sxs-lookup"><span data-stu-id="573e3-113">Many Windows features have an associated WMI provider that exposes their management capabilities.</span></span> <span data-ttu-id="573e3-114">Чтобы получить поставщики WMI, выполните запрос WMI, который получает экземпляры класса __Provider WMI, например следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="573e3-114">To get WMI providers, run a WMI query that gets instances of the __Provider WMI class, such as the following query.</span></span>

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a><span data-ttu-id="573e3-115">ТРИ КОМПОНЕНТА ИНСТРУМЕНТАРИЯ WMI</span><span class="sxs-lookup"><span data-stu-id="573e3-115">THREE COMPONENTS OF WMI</span></span>

<span data-ttu-id="573e3-116">Следующие три компонента WMI взаимодействуют с Windows PowerShell: пространствами имен, поставщиками и классами.</span><span class="sxs-lookup"><span data-stu-id="573e3-116">The following three components of WMI interact with Windows PowerShell: Namespaces, Providers, and Classes.</span></span>

<span data-ttu-id="573e3-117">Пространства имен WMI упорядочивают поставщиков WMI и классы WMI в группы связанных компонентов.</span><span class="sxs-lookup"><span data-stu-id="573e3-117">WMI Namespaces organize WMI providers and WMI classes into groups of related components.</span></span> <span data-ttu-id="573e3-118">Таким образом, они похожи на .NET Framework пространства имен.</span><span class="sxs-lookup"><span data-stu-id="573e3-118">In this way, they are similar to .NET Framework namespaces.</span></span>
<span data-ttu-id="573e3-119">Пространства имен не являются физическими расположениями, но более подобны логическим базам данных.</span><span class="sxs-lookup"><span data-stu-id="573e3-119">Namespaces are not physical locations, but are more like logical databases.</span></span>
<span data-ttu-id="573e3-120">Все пространства имен WMI являются экземплярами класса __Namespace системы.</span><span class="sxs-lookup"><span data-stu-id="573e3-120">All WMI namespaces are instances of the __Namespace system class.</span></span> <span data-ttu-id="573e3-121">Пространством имен WMI по умолчанию является root \/ CIMV2 (начиная с Microsoft Windows 2000).</span><span class="sxs-lookup"><span data-stu-id="573e3-121">The default WMI namespace is Root\/CIMV2 (since Microsoft Windows 2000).</span></span> <span data-ttu-id="573e3-122">Чтобы использовать Windows PowerShell для получения пространств имен WMI в текущем сеансе, используйте команду в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="573e3-122">To use Windows PowerShell to get WMI namespaces in the current session, use a command with the following format.</span></span>

```powershell
Get-WmiObject -Class __Namespace
```

<span data-ttu-id="573e3-123">Чтобы получить пространства имен WMI в других пространствах имен, используйте параметр Namespace, чтобы изменить расположение поиска.</span><span class="sxs-lookup"><span data-stu-id="573e3-123">To get WMI namespaces in other namespaces, use the Namespace parameter to change the location of the search.</span></span> <span data-ttu-id="573e3-124">Следующая команда находит пространства имен WMI, расположенные в пространстве имен root/cimv2/Applications.</span><span class="sxs-lookup"><span data-stu-id="573e3-124">The following command finds WMI namespaces that reside in the Root/Cimv2/Applications namespace.</span></span>

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

<span data-ttu-id="573e3-125">Пространства имен WMI являются иерархическими.</span><span class="sxs-lookup"><span data-stu-id="573e3-125">WMI namespaces are hierarchical.</span></span> <span data-ttu-id="573e3-126">Поэтому получение списка всех пространств имен в определенной системе требует выполнения рекурсивного запроса, начиная с корневого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="573e3-126">Therefore, obtaining a list of all namespaces on a particular system requires performing a recursive query starting at the root namespace.</span></span>

<span data-ttu-id="573e3-127">Поставщики WMI предоставляют сведения об управляемых объектах Windows.</span><span class="sxs-lookup"><span data-stu-id="573e3-127">WMI Providers expose information about Windows manageable objects.</span></span> <span data-ttu-id="573e3-128">Поставщик получает данные из компонента и передает эти данные через инструментарий WMI в приложение управления, например Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="573e3-128">A provider retrieves data from a component, and passes that data through WMI to a management application, such as Windows PowerShell.</span></span> <span data-ttu-id="573e3-129">Большинство поставщиков WMI являются динамическими поставщиками. Это означает, что они получают данные динамически, когда они запрашиваются через приложение управления.</span><span class="sxs-lookup"><span data-stu-id="573e3-129">Most WMI providers are dynamic providers, which means that they obtain the data dynamically when it is requested through the management application.</span></span>

## <a name="finding-wmi-classes"></a><span data-ttu-id="573e3-130">ПОИСК КЛАССОВ WMI</span><span class="sxs-lookup"><span data-stu-id="573e3-130">FINDING WMI CLASSES</span></span>

<span data-ttu-id="573e3-131">При установке Windows 8 по умолчанию существует более 1 100 классов WMI в корневом \/ CIMV2.</span><span class="sxs-lookup"><span data-stu-id="573e3-131">In a default installation of Windows 8, there are more than 1,100 WMI classes in Root\/Cimv2.</span></span> <span data-ttu-id="573e3-132">С помощью этого множества классов WMI задача будет определять соответствующий класс WMI для выполнения определенной задачи.</span><span class="sxs-lookup"><span data-stu-id="573e3-132">With this many WMI classes, the challenge becomes identifying the appropriate WMI class to use to perform a specific task.</span></span> <span data-ttu-id="573e3-133">Windows PowerShell 3,0 предоставляет два способа поиска классов WMI, связанных с конкретным разделом.</span><span class="sxs-lookup"><span data-stu-id="573e3-133">Windows PowerShell 3.0 provides two ways to find WMI classes that are related to a specific topic.</span></span>

<span data-ttu-id="573e3-134">Например, чтобы найти классы WMI в корневом \\ пространстве имен CIMV2 WMI, связанных с дисками, можно использовать такой запрос, как показано здесь.</span><span class="sxs-lookup"><span data-stu-id="573e3-134">For example,to find WMI classes in the root\\CIMV2 WMI namespace that are related to disks, you can use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *disk*
```

<span data-ttu-id="573e3-135">Для поиска классов WMI, связанных с памятью, можно использовать такой запрос, как показано здесь.</span><span class="sxs-lookup"><span data-stu-id="573e3-135">To find WMI classes that are related to memory, you might use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *memory*
```

<span data-ttu-id="573e3-136">Командлеты CIM также предоставляют возможность обнаружения классов WMI.</span><span class="sxs-lookup"><span data-stu-id="573e3-136">The CIM cmdlets also provide the ability to discover WMI classes.</span></span> <span data-ttu-id="573e3-137">Для этого используйте командлет Get-CIMClass.</span><span class="sxs-lookup"><span data-stu-id="573e3-137">To do this, use the Get-CIMClass cmdlet.</span></span> <span data-ttu-id="573e3-138">Приведенная здесь команда выводит список классов WMI, связанных с видео.</span><span class="sxs-lookup"><span data-stu-id="573e3-138">The command shown here lists WMI classes related to video.</span></span>

```powershell
Get-CimClass *video*
```

<span data-ttu-id="573e3-139">Расширение табуляции работает при изменении пространств имен WMI, поэтому при использовании расширения клавиши TAB можно легко обнаруживать подразделы WMI.</span><span class="sxs-lookup"><span data-stu-id="573e3-139">Tab expansion works when changing WMI namespaces, and therefore use of tab expansion makes sub-WMI namespaces easily discoverable.</span></span> <span data-ttu-id="573e3-140">В следующем примере командлет Get-CimClass перечисляет классы WMI, связанные с параметрами питания.</span><span class="sxs-lookup"><span data-stu-id="573e3-140">In the following example, the Get-CimClass cmdlet lists WMI classes related to power settings.</span></span>
<span data-ttu-id="573e3-141">Чтобы найти его, введите `root/CIMV2/` пространство имен и нажмите клавишу TAB несколько раз, пока не появится пространство имен Power.</span><span class="sxs-lookup"><span data-stu-id="573e3-141">To find it, type the `root/CIMV2/` namespace and then press the Tab key several times until the power namespace appears.</span></span> <span data-ttu-id="573e3-142">Вот нужная команда:</span><span class="sxs-lookup"><span data-stu-id="573e3-142">Here is the command:</span></span>

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
