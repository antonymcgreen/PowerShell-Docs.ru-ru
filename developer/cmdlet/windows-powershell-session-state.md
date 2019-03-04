---
title: Состояние сеанса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.assetid: 74912940-2b10-4a76-b174-6d035d71c02b
caps.latest.revision: 8
ms.openlocfilehash: 5d4effb508c9f2544832dad557671520cb0a7ac7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862990"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="05e24-102">Состояние сеанса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e24-102">Windows PowerShell Session State</span></span>

<span data-ttu-id="05e24-103">Состояние сеанса относится к текущей конфигурации сеанса Windows PowerShell или модуля.</span><span class="sxs-lookup"><span data-stu-id="05e24-103">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="05e24-104">Сеанс Windows PowerShell — операционную среду с интерактивного использования пользователем командной строки, или программным образом ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="05e24-104">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="05e24-105">Состояние сеанса для сеанса называется глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="05e24-105">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="05e24-106">С точки зрения разработчика сеанс Windows PowerShell — это время между при открытии пространства выполнения Windows PowerShell в ведущее приложение и при его закрытии пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="05e24-106">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="05e24-107">Сеанс рассмотрели другим способом, и составляет время жизни экземпляра ядра Windows PowerShell, который вызывается, пока существует пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="05e24-107">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="05e24-108">Состояние сеанса модуля</span><span class="sxs-lookup"><span data-stu-id="05e24-108">Module Session State</span></span>

<span data-ttu-id="05e24-109">Модуль состояния сеанса создаются каждый раз, когда модуль или одного из его вложенные модули не импортированы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="05e24-109">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="05e24-110">Когда модуль экспортирует элемент, такой как командлета, функции или сценарии, ссылку на этот элемент добавляется в глобальное состояние сеанса сеанса.</span><span class="sxs-lookup"><span data-stu-id="05e24-110">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="05e24-111">Тем не менее при запуске элемента, она выполняется в состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="05e24-111">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="05e24-112">Данные о состоянии сеанса</span><span class="sxs-lookup"><span data-stu-id="05e24-112">Session-State Data</span></span>

<span data-ttu-id="05e24-113">Данные о состоянии сеанса может быть открытым или закрытым.</span><span class="sxs-lookup"><span data-stu-id="05e24-113">Session state data can be public or private.</span></span> <span data-ttu-id="05e24-114">Общедоступные данные, позволяющих вызовы из за пределами состояние сеанса, хотя личных данных доступен только для вызовов из состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="05e24-114">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="05e24-115">Например, модуль может иметь закрытой функции, который может быть вызван только модулем или только для внутреннего использования, общим элементам, которые были экспортированы.</span><span class="sxs-lookup"><span data-stu-id="05e24-115">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="05e24-116">Это похоже на частные и общедоступные члены типа платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05e24-116">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="05e24-117">Данные о состоянии сеанса хранится в текущем экземпляре ядра выполнения в контексте текущего сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05e24-117">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="05e24-118">Данные о состоянии сеанса состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="05e24-118">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="05e24-119">Сведения о пути</span><span class="sxs-lookup"><span data-stu-id="05e24-119">Path information</span></span>

- <span data-ttu-id="05e24-120">Сведения о диске</span><span class="sxs-lookup"><span data-stu-id="05e24-120">Drive information</span></span>

- <span data-ttu-id="05e24-121">Сведения о поставщике Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e24-121">Windows PowerShell provider information</span></span>

- <span data-ttu-id="05e24-122">Сведения об импортированных модулей и ссылки на элементы модуля (например, командлеты, функции и сценарии), которые экспортируются модулем.</span><span class="sxs-lookup"><span data-stu-id="05e24-122">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="05e24-123">Эти сведения и эти ссылки предназначены для глобальное состояние сеанса только.</span><span class="sxs-lookup"><span data-stu-id="05e24-123">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="05e24-124">Сведения о переменных состояния сеанса</span><span class="sxs-lookup"><span data-stu-id="05e24-124">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="05e24-125">Доступ к данным состояния сеанса в командлеты</span><span class="sxs-lookup"><span data-stu-id="05e24-125">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="05e24-126">Командлеты можно получить доступ к данным состояния сеанса либо косвенно через [System.Management.Automation.Pscmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) свойство класса командлета или напрямую через [ System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) класса.</span><span class="sxs-lookup"><span data-stu-id="05e24-126">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.Pscmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="05e24-127">[System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) класс предоставляет свойства, которые можно использовать для изучения различных типов данных состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="05e24-127">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="05e24-128">См. также</span><span class="sxs-lookup"><span data-stu-id="05e24-128">See Also</span></span>

[<span data-ttu-id="05e24-129">System.Management.Automation.Pscmdlet.Sessionstate</span><span class="sxs-lookup"><span data-stu-id="05e24-129">System.Management.Automation.Pscmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="05e24-130">System.Management.Automation.Sessionstate? Displayproperty = Fullname</span><span class="sxs-lookup"><span data-stu-id="05e24-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="05e24-131">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e24-131">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="05e24-132">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e24-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="05e24-133">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="05e24-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
