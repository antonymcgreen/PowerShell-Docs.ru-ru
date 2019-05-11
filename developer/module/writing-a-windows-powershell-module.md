---
title: Написание модуля Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229345"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="4f4e4-102">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-102">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="4f4e4-103">Этот документ был написан для администраторов, скрипт разработчикам и разработчикам командлетов, которым необходимо создание и распространение их командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-103">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4f4e4-104">С помощью модулей Windows PowerShell, можно упаковать и распространить свои решения Windows PowerShell без использования скомпилированный язык.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-104">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="4f4e4-105">Модули Windows PowerShell для его секции, упорядочивать и абстрагировать код Windows PowerShell в автономной и многократно используемых единиц.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-105">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="4f4e4-106">Эти единицы для повторного использования вы можете легко обмениваться модули непосредственно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-106">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="4f4e4-107">Если вы являетесь разработчиком скрипт, вы можете также переупаковать сторонних модулей, чтобы создавать пользовательские приложения на основе сценария.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-107">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="4f4e4-108">Модули, аналогичную модулям в других языках сценариев, таких как Perl и Python, включения решений со сценариями готовый к выпуску, использующих многократно используемых, распространяемые компоненты, с дополнительными преимуществами, поскольку позволяет не делать одну и абстрагировать несколько компонентов для Создание пользовательских решений.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-108">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="4f4e4-109">В их основных Windows PowerShell будет рассматривать любой допустимый код сценария Windows PowerShell, сохраненные в файле с расширением psm1 как модуль.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-109">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="4f4e4-110">PowerShell также автоматически обрабатывает любую сборку двоичных командлет как модуль.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-110">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="4f4e4-111">Тем не менее можно также использовать модуль (или точнее, манифеста модуля), объединить всего решения.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-111">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="4f4e4-112">Следующие сценарии описывают типичные способы использования модулей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-112">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="4f4e4-113">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="4f4e4-113">Libraries</span></span>

<span data-ttu-id="4f4e4-114">Модули можно использовать для упаковки и распространения связный библиотеки функций для выполнения типичных задач.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-114">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="4f4e4-115">Как правило имена этих функций, совместно использовать один или несколько существительных, отражающих типичную задачу, они используются для.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-115">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="4f4e4-116">Эти функции также может быть аналогичную классов .NET Framework, в том, что они могут иметь открытым и закрытым элементам.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-116">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="4f4e4-117">Например библиотеку может содержать набор функций для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-117">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="4f4e4-118">В этом случае существительное, отражая общие задачи может быть «файл».</span><span class="sxs-lookup"><span data-stu-id="4f4e4-118">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="4f4e4-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4f4e4-119">Configuration</span></span>

<span data-ttu-id="4f4e4-120">Модули можно использовать для настройки вашей среды, добавив определенные командлеты, поставщики, функции и переменные.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-120">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="4f4e4-121">Скомпилированный код разработки и распространения</span><span class="sxs-lookup"><span data-stu-id="4f4e4-121">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="4f4e4-122">Командлетов и поставщиков разработчики могут использовать модули для тестирования и распространения их скомпилированного кода без необходимости создания оснастки. Их можно импортировать сборку, содержащую скомпилированный код в виде модуля (двоичный модуль) без необходимости создания и регистрации оснастки.</span><span class="sxs-lookup"><span data-stu-id="4f4e4-122">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f4e4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4f4e4-123">See Also</span></span>

[<span data-ttu-id="4f4e4-124">Основные сведения о модуле Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-124">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="4f4e4-125">Как написать модуль сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-125">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="4f4e4-126">Как написать модуль двоичных файлов PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-126">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="4f4e4-127">Как создать манифест модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-127">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="4f4e4-128">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="4f4e4-128">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="4f4e4-129">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-129">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="4f4e4-130">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4e4-130">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
