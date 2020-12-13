---
ms.date: 09/13/2016
ms.topic: reference
title: Состояние сеанса Windows PowerShell
description: Состояние сеанса Windows PowerShell
ms.openlocfilehash: 51de92f1f392f708cf49c7ccb4a6808fd628076c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668139"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="38881-103">Состояние сеанса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38881-103">Windows PowerShell Session State</span></span>

<span data-ttu-id="38881-104">Состояние сеанса относится к текущей конфигурации сеанса или модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38881-104">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="38881-105">Сеанс Windows PowerShell — это Рабочая среда, используемая пользователем командной строки в интерактивном режиме или программно ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="38881-105">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="38881-106">Состояние сеанса для сеанса называется глобальным состоянием сеанса.</span><span class="sxs-lookup"><span data-stu-id="38881-106">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="38881-107">С точки зрения разработчика, сеанс Windows PowerShell ссылается на время между открытием пространства выполнения Windows PowerShell и его закрытием.</span><span class="sxs-lookup"><span data-stu-id="38881-107">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="38881-108">В другом случае сеанс является временем существования экземпляра обработчика Windows PowerShell, который вызывается, пока существует пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="38881-108">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="38881-109">Состояние сеанса модуля</span><span class="sxs-lookup"><span data-stu-id="38881-109">Module Session State</span></span>

<span data-ttu-id="38881-110">Состояния сеанса модуля создаются всякий раз, когда модуль или один из его вложенных модулей импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="38881-110">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="38881-111">Когда модуль экспортирует элемент, например командлет, функцию или скрипт, в глобальное состояние сеанса в сеансе добавляется ссылка на этот элемент.</span><span class="sxs-lookup"><span data-stu-id="38881-111">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="38881-112">Однако при выполнении элемента он выполняется в состоянии сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="38881-112">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="38881-113">Session-State данных</span><span class="sxs-lookup"><span data-stu-id="38881-113">Session-State Data</span></span>

<span data-ttu-id="38881-114">Данные состояния сеанса могут быть открытыми или закрытыми.</span><span class="sxs-lookup"><span data-stu-id="38881-114">Session state data can be public or private.</span></span> <span data-ttu-id="38881-115">Общедоступные данные доступны для вызовов извне состояния сеанса, в то время как закрытые данные доступны только для вызовов в состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="38881-115">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="38881-116">Например, модуль может иметь закрытую функцию, которая может быть вызвана только модулем или внутренним экспортируемым открытым элементом.</span><span class="sxs-lookup"><span data-stu-id="38881-116">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="38881-117">Это похоже на закрытый и открытый члены типа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38881-117">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="38881-118">Данные состояния сеанса хранятся в текущем экземпляре подсистемы выполнения в контексте текущего сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38881-118">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="38881-119">Данные состояния сеанса состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="38881-119">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="38881-120">Сведения о пути</span><span class="sxs-lookup"><span data-stu-id="38881-120">Path information</span></span>

- <span data-ttu-id="38881-121">Сведения о диске</span><span class="sxs-lookup"><span data-stu-id="38881-121">Drive information</span></span>

- <span data-ttu-id="38881-122">Сведения о поставщике Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38881-122">Windows PowerShell provider information</span></span>

- <span data-ttu-id="38881-123">Сведения о импортированных модулях и ссылках на элементы модуля (например, командлеты, функции и скрипты), которые экспортируются модулем.</span><span class="sxs-lookup"><span data-stu-id="38881-123">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="38881-124">Эти сведения и эти ссылки предназначены только для глобального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="38881-124">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="38881-125">Сведения о переменной состояния сеанса</span><span class="sxs-lookup"><span data-stu-id="38881-125">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="38881-126">Доступ к данным Session-State в командлетах</span><span class="sxs-lookup"><span data-stu-id="38881-126">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="38881-127">Командлеты могут обращаться к данным состояния сеанса непрямо через свойство [System. Management. Automation. PSCmdlet. sessionState \*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) класса командлета или напрямую через класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) .</span><span class="sxs-lookup"><span data-stu-id="38881-127">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="38881-128">Класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) предоставляет свойства, которые можно использовать для анализа различных типов данных состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="38881-128">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="38881-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="38881-129">See Also</span></span>

[<span data-ttu-id="38881-130">System. Management. Automation. PSCmdlet. sessionState</span><span class="sxs-lookup"><span data-stu-id="38881-130">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="38881-131">System. Management. Automation. sessionState? DisplayProperty = FullName</span><span class="sxs-lookup"><span data-stu-id="38881-131">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="38881-132">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38881-132">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="38881-133">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38881-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="38881-134">Пакет SDK Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38881-134">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
