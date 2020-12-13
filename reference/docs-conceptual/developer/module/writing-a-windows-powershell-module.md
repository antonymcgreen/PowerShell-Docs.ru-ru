---
ms.date: 09/13/2016
ms.topic: reference
title: Написание модуля Windows PowerShell
description: Написание модуля Windows PowerShell
ms.openlocfilehash: 307241f0fb4d12c1a5cbd651a0ae4d5303098b27
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659425"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="32b87-103">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-103">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="32b87-104">Этот документ предназначен для администраторов, разработчиков скриптов и разработчиков командлетов, которым необходимо упаковать и распространить свои командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32b87-104">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="32b87-105">С помощью модулей Windows PowerShell можно упаковывать и распространять решения Windows PowerShell без использования скомпилированного языка.</span><span class="sxs-lookup"><span data-stu-id="32b87-105">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="32b87-106">Модули Windows PowerShell позволяют секционировать, упорядочивать и систематизировать код Windows PowerShell в автономных, многократно используемых единицах.</span><span class="sxs-lookup"><span data-stu-id="32b87-106">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="32b87-107">С помощью этих многократно используемых модулей можно легко предоставить доступ к модулям напрямую другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="32b87-107">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="32b87-108">Если вы являетесь разработчиком скриптов, вы также можете повторно упаковать сторонние модули для создания пользовательских приложений на основе сценариев.</span><span class="sxs-lookup"><span data-stu-id="32b87-108">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="32b87-109">Модули, аналогичные модулям в других языках сценариев, таких как Perl и Python, обеспечивают готовые к работе решения сценариев, использующие многократно используемые, распространяемые компоненты с дополнительным преимуществом, позволяющим переупаковать и составить абстрактные компоненты, чтобы создать пользовательские решения.</span><span class="sxs-lookup"><span data-stu-id="32b87-109">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="32b87-110">В большинстве случаев Windows PowerShell будет обрабатывать любой допустимый код сценария Windows PowerShell, сохраненный в файле. PSM1 в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="32b87-110">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="32b87-111">PowerShell также будет автоматически обрабатывать любую сборку двоичных командлетов как модуль.</span><span class="sxs-lookup"><span data-stu-id="32b87-111">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="32b87-112">Однако можно также использовать модуль (или более конкретно, манифест модуля) для объединения всего решения.</span><span class="sxs-lookup"><span data-stu-id="32b87-112">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="32b87-113">В следующих сценариях описываются типичные варианты использования модулей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32b87-113">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="32b87-114">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="32b87-114">Libraries</span></span>

<span data-ttu-id="32b87-115">Модули можно использовать для упаковки и распространения согласованных библиотек функций, выполняющих стандартные задачи.</span><span class="sxs-lookup"><span data-stu-id="32b87-115">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="32b87-116">Как правило, имена этих функций имеют одно или несколько существительных, отражающих общую задачу, для которой они используются.</span><span class="sxs-lookup"><span data-stu-id="32b87-116">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="32b87-117">Эти функции также могут быть похожи на .NET Framework классы в том, что они могут иметь открытые и закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="32b87-117">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="32b87-118">Например, Библиотека может содержать набор функций для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="32b87-118">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="32b87-119">В этом случае существительное, отражающее общую задачу, может быть «File».</span><span class="sxs-lookup"><span data-stu-id="32b87-119">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="32b87-120">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="32b87-120">Configuration</span></span>

<span data-ttu-id="32b87-121">Модули можно использовать для настройки среды путем добавления конкретных командлетов, поставщиков, функций и переменных.</span><span class="sxs-lookup"><span data-stu-id="32b87-121">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="32b87-122">Разработка и распространение скомпилированного кода</span><span class="sxs-lookup"><span data-stu-id="32b87-122">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="32b87-123">Разработчики командлетов и поставщиков могут использовать модули для тестирования и распространения скомпилированного кода без необходимости создавать оснастки. Они могут импортировать сборку, содержащую скомпилированный код, в виде модуля (двоичный модуль) без необходимости создавать и регистрировать оснастки.</span><span class="sxs-lookup"><span data-stu-id="32b87-123">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="32b87-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="32b87-124">See Also</span></span>

[<span data-ttu-id="32b87-125">Общие сведения о модулях Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-125">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="32b87-126">Как написать модуль сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-126">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="32b87-127">Как написать бинарный модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-127">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="32b87-128">Как написать манифест модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-128">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="32b87-129">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="32b87-129">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="32b87-130">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-130">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="32b87-131">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b87-131">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
