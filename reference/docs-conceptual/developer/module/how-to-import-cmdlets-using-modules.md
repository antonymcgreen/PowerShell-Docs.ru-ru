---
ms.date: 08/28/2019
ms.topic: reference
title: Импорт командлетов с помощью модулей
description: Импорт командлетов с помощью модулей
ms.openlocfilehash: 485a4be4d2accaf050a6536e7f92a0673f62a30b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657281"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="82590-103">Импорт командлетов с помощью модулей</span><span class="sxs-lookup"><span data-stu-id="82590-103">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="82590-104">В этой статье описывается, как импортировать командлеты в сеанс PowerShell с помощью двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="82590-104">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="82590-105">Членами модулей могут быть командлеты, поставщики, функции, переменные, псевдонимы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="82590-105">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="82590-106">Оснастки могут содержать только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="82590-106">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="82590-107">Как загружать командлеты с помощью модуля</span><span class="sxs-lookup"><span data-stu-id="82590-107">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="82590-108">Создайте папку модуля, имя которой совпадает с именем файла сборки, в котором реализуются командлеты.</span><span class="sxs-lookup"><span data-stu-id="82590-108">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="82590-109">В этой процедуре папка Module создается в `system32` папке Windows.</span><span class="sxs-lookup"><span data-stu-id="82590-109">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="82590-110">Убедитесь, что `PSModulePath` переменная среды содержит путь к новой папке модуля.</span><span class="sxs-lookup"><span data-stu-id="82590-110">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="82590-111">По умолчанию системная папка уже добавлена в `PSModulePath` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="82590-111">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="82590-112">Чтобы просмотреть `PSModulePath` , введите: `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="82590-112">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="82590-113">Скопируйте сборку командлета в папку Module.</span><span class="sxs-lookup"><span data-stu-id="82590-113">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="82590-114">Добавьте файл манифеста модуля ( `.psd1` ) в корневую папку модуля.</span><span class="sxs-lookup"><span data-stu-id="82590-114">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="82590-115">PowerShell использует манифест модуля для импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="82590-115">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="82590-116">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="82590-116">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="82590-117">Выполните следующую команду, чтобы добавить командлеты в сеанс:</span><span class="sxs-lookup"><span data-stu-id="82590-117">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="82590-118">Эту процедуру можно использовать для проверки командлетов.</span><span class="sxs-lookup"><span data-stu-id="82590-118">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="82590-119">Он добавляет все командлеты в сборку в сеанс.</span><span class="sxs-lookup"><span data-stu-id="82590-119">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="82590-120">Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="82590-120">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82590-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="82590-121">See also</span></span>

[<span data-ttu-id="82590-122">Как написать манифест модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="82590-122">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="82590-123">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="82590-123">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="82590-124">Import-Module</span><span class="sxs-lookup"><span data-stu-id="82590-124">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="82590-125">Установка модулей</span><span class="sxs-lookup"><span data-stu-id="82590-125">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="82590-126">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="82590-126">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="82590-127">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82590-127">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
