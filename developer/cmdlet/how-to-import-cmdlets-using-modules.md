---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 2f145795a57c988da0cb4ed294142aa141c53cae
ms.sourcegitcommit: 02eed65c526ef19cf952c2129f280bb5615bf0c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70215276"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="b7e32-102">Импорт командлетов с помощью модулей</span><span class="sxs-lookup"><span data-stu-id="b7e32-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="b7e32-103">В этой статье описывается, как импортировать командлеты в сеанс PowerShell с помощью двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="b7e32-103">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="b7e32-104">Членами модулей могут быть командлеты, поставщики, функции, переменные, псевдонимы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b7e32-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="b7e32-105">Оснастки могут содержать только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="b7e32-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="b7e32-106">Как загружать командлеты с помощью модуля</span><span class="sxs-lookup"><span data-stu-id="b7e32-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="b7e32-107">Создайте папку модуля, имя которой совпадает с именем файла сборки, в котором реализуются командлеты.</span><span class="sxs-lookup"><span data-stu-id="b7e32-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="b7e32-108">В этой процедуре папка Module создается в папке Windows `system32` .</span><span class="sxs-lookup"><span data-stu-id="b7e32-108">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="b7e32-109">Убедитесь, что `PSModulePath` переменная среды содержит путь к новой папке модуля.</span><span class="sxs-lookup"><span data-stu-id="b7e32-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="b7e32-110">По умолчанию системная папка уже добавлена в `PSModulePath` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="b7e32-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="b7e32-111">Чтобы просмотреть `PSModulePath`, введите: `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="b7e32-111">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="b7e32-112">Скопируйте сборку командлета в папку Module.</span><span class="sxs-lookup"><span data-stu-id="b7e32-112">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="b7e32-113">Добавьте файл манифеста модуля (`.psd1`) в корневую папку модуля.</span><span class="sxs-lookup"><span data-stu-id="b7e32-113">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="b7e32-114">PowerShell использует манифест модуля для импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="b7e32-114">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="b7e32-115">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="b7e32-115">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="b7e32-116">Выполните следующую команду, чтобы добавить командлеты в сеанс:</span><span class="sxs-lookup"><span data-stu-id="b7e32-116">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="b7e32-117">Эту процедуру можно использовать для проверки командлетов.</span><span class="sxs-lookup"><span data-stu-id="b7e32-117">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="b7e32-118">Он добавляет все командлеты в сборку в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b7e32-118">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="b7e32-119">Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="b7e32-119">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7e32-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7e32-120">See also</span></span>

[<span data-ttu-id="b7e32-121">Написание манифеста модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7e32-121">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="b7e32-122">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7e32-122">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="b7e32-123">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b7e32-123">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="b7e32-124">Установка модулей</span><span class="sxs-lookup"><span data-stu-id="b7e32-124">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="b7e32-125">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="b7e32-125">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="b7e32-126">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7e32-126">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
