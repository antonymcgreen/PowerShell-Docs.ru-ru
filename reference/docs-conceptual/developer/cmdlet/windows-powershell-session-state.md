---
title: Состояние сеанса Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.openlocfilehash: 7436e3ebd0e099ead81f9fea01a0a2994b982213
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783948"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="9a5da-102">Состояние сеанса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a5da-102">Windows PowerShell Session State</span></span>

<span data-ttu-id="9a5da-103">Состояние сеанса относится к текущей конфигурации сеанса или модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5da-103">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="9a5da-104">Сеанс Windows PowerShell — это Рабочая среда, используемая пользователем командной строки в интерактивном режиме или программно ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="9a5da-104">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="9a5da-105">Состояние сеанса для сеанса называется глобальным состоянием сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a5da-105">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="9a5da-106">С точки зрения разработчика, сеанс Windows PowerShell ссылается на время между открытием пространства выполнения Windows PowerShell и его закрытием.</span><span class="sxs-lookup"><span data-stu-id="9a5da-106">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="9a5da-107">В другом случае сеанс является временем существования экземпляра обработчика Windows PowerShell, который вызывается, пока существует пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a5da-107">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="9a5da-108">Состояние сеанса модуля</span><span class="sxs-lookup"><span data-stu-id="9a5da-108">Module Session State</span></span>

<span data-ttu-id="9a5da-109">Состояния сеанса модуля создаются всякий раз, когда модуль или один из его вложенных модулей импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="9a5da-109">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="9a5da-110">Когда модуль экспортирует элемент, например командлет, функцию или скрипт, в глобальное состояние сеанса в сеансе добавляется ссылка на этот элемент.</span><span class="sxs-lookup"><span data-stu-id="9a5da-110">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="9a5da-111">Однако при выполнении элемента он выполняется в состоянии сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="9a5da-111">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="9a5da-112">Данные состояния сеанса</span><span class="sxs-lookup"><span data-stu-id="9a5da-112">Session-State Data</span></span>

<span data-ttu-id="9a5da-113">Данные состояния сеанса могут быть открытыми или закрытыми.</span><span class="sxs-lookup"><span data-stu-id="9a5da-113">Session state data can be public or private.</span></span> <span data-ttu-id="9a5da-114">Общедоступные данные доступны для вызовов извне состояния сеанса, в то время как закрытые данные доступны только для вызовов в состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a5da-114">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="9a5da-115">Например, модуль может иметь закрытую функцию, которая может быть вызвана только модулем или внутренним экспортируемым открытым элементом.</span><span class="sxs-lookup"><span data-stu-id="9a5da-115">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="9a5da-116">Это похоже на закрытый и открытый члены типа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a5da-116">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="9a5da-117">Данные состояния сеанса хранятся в текущем экземпляре подсистемы выполнения в контексте текущего сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5da-117">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="9a5da-118">Данные состояния сеанса состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="9a5da-118">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="9a5da-119">Сведения о пути</span><span class="sxs-lookup"><span data-stu-id="9a5da-119">Path information</span></span>

- <span data-ttu-id="9a5da-120">Сведения о диске</span><span class="sxs-lookup"><span data-stu-id="9a5da-120">Drive information</span></span>

- <span data-ttu-id="9a5da-121">Сведения о поставщике Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a5da-121">Windows PowerShell provider information</span></span>

- <span data-ttu-id="9a5da-122">Сведения о импортированных модулях и ссылках на элементы модуля (например, командлеты, функции и скрипты), которые экспортируются модулем.</span><span class="sxs-lookup"><span data-stu-id="9a5da-122">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="9a5da-123">Эти сведения и эти ссылки предназначены только для глобального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a5da-123">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="9a5da-124">Сведения о переменной состояния сеанса</span><span class="sxs-lookup"><span data-stu-id="9a5da-124">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="9a5da-125">Доступ к данным состояния сеанса в командлетах</span><span class="sxs-lookup"><span data-stu-id="9a5da-125">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="9a5da-126">Командлеты могут обращаться к данным состояния сеанса непрямо через свойство [System. Management. Automation. PSCmdlet. sessionState \*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) класса командлета или напрямую через класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) .</span><span class="sxs-lookup"><span data-stu-id="9a5da-126">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="9a5da-127">Класс [System. Management. Automation. sessionState](/dotnet/api/System.Management.Automation.SessionState) предоставляет свойства, которые можно использовать для анализа различных типов данных состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a5da-127">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a5da-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9a5da-128">See Also</span></span>

[<span data-ttu-id="9a5da-129">System. Management. Automation. PSCmdlet. sessionState</span><span class="sxs-lookup"><span data-stu-id="9a5da-129">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="9a5da-130">System. Management. Automation. sessionState? DisplayProperty = FullName</span><span class="sxs-lookup"><span data-stu-id="9a5da-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="9a5da-131">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a5da-131">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="9a5da-132">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a5da-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="9a5da-133">Пакет SDK оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a5da-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
