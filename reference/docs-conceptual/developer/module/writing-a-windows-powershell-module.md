---
title: Создание модуля Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360623"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="44dd0-102">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-102">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="44dd0-103">Этот документ предназначен для администраторов, разработчиков скриптов и разработчиков командлетов, которым необходимо упаковать и распространить свои командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44dd0-103">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="44dd0-104">С помощью модулей Windows PowerShell можно упаковывать и распространять решения Windows PowerShell без использования скомпилированного языка.</span><span class="sxs-lookup"><span data-stu-id="44dd0-104">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="44dd0-105">Модули Windows PowerShell позволяют секционировать, упорядочивать и систематизировать код Windows PowerShell в автономных, многократно используемых единицах.</span><span class="sxs-lookup"><span data-stu-id="44dd0-105">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="44dd0-106">С помощью этих многократно используемых модулей можно легко предоставить доступ к модулям напрямую другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="44dd0-106">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="44dd0-107">Если вы являетесь разработчиком скриптов, вы также можете повторно упаковать сторонние модули для создания пользовательских приложений на основе сценариев.</span><span class="sxs-lookup"><span data-stu-id="44dd0-107">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="44dd0-108">Модули, аналогичные модулям на других языках сценариев, таких как Perl и Python, обеспечивают готовые к работе решения сценариев, использующие многократно используемые, распространяемые компоненты с дополнительным преимуществом, позволяющим переупаковку и абстракцию нескольких компонентов в Создание пользовательских решений.</span><span class="sxs-lookup"><span data-stu-id="44dd0-108">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="44dd0-109">В большинстве случаев Windows PowerShell будет обрабатывать любой допустимый код сценария Windows PowerShell, сохраненный в файле. PSM1 в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="44dd0-109">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="44dd0-110">PowerShell также будет автоматически обрабатывать любую сборку двоичных командлетов как модуль.</span><span class="sxs-lookup"><span data-stu-id="44dd0-110">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="44dd0-111">Однако можно также использовать модуль (или более конкретно, манифест модуля) для объединения всего решения.</span><span class="sxs-lookup"><span data-stu-id="44dd0-111">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="44dd0-112">В следующих сценариях описываются типичные варианты использования модулей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44dd0-112">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="44dd0-113">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="44dd0-113">Libraries</span></span>

<span data-ttu-id="44dd0-114">Модули можно использовать для упаковки и распространения согласованных библиотек функций, выполняющих стандартные задачи.</span><span class="sxs-lookup"><span data-stu-id="44dd0-114">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="44dd0-115">Как правило, имена этих функций имеют одно или несколько существительных, отражающих общую задачу, для которой они используются.</span><span class="sxs-lookup"><span data-stu-id="44dd0-115">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="44dd0-116">Эти функции также могут быть похожи на .NET Framework классы в том, что они могут иметь открытые и закрытые члены.</span><span class="sxs-lookup"><span data-stu-id="44dd0-116">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="44dd0-117">Например, Библиотека может содержать набор функций для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="44dd0-117">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="44dd0-118">В этом случае существительное, отражающее общую задачу, может быть «File».</span><span class="sxs-lookup"><span data-stu-id="44dd0-118">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="44dd0-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="44dd0-119">Configuration</span></span>

<span data-ttu-id="44dd0-120">Модули можно использовать для настройки среды путем добавления конкретных командлетов, поставщиков, функций и переменных.</span><span class="sxs-lookup"><span data-stu-id="44dd0-120">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="44dd0-121">Разработка и распространение скомпилированного кода</span><span class="sxs-lookup"><span data-stu-id="44dd0-121">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="44dd0-122">Разработчики командлетов и поставщиков могут использовать модули для тестирования и распространения скомпилированного кода без необходимости создавать оснастки. Они могут импортировать сборку, содержащую скомпилированный код, в виде модуля (двоичный модуль) без необходимости создавать и регистрировать оснастки.</span><span class="sxs-lookup"><span data-stu-id="44dd0-122">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="44dd0-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="44dd0-123">See Also</span></span>

[<span data-ttu-id="44dd0-124">Основные сведения о модуле Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-124">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="44dd0-125">Написание модуля скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-125">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="44dd0-126">Написание двоичного модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-126">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="44dd0-127">Написание манифеста модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-127">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="44dd0-128">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="44dd0-128">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="44dd0-129">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-129">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="44dd0-130">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="44dd0-130">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
