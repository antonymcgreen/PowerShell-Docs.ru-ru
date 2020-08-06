---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.date: 08/28/2019
ms.openlocfilehash: fa8d629c14b06e3f9e9d6151cf09aa6b4acce358
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779375"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="43637-102">Импорт командлетов с помощью модулей</span><span class="sxs-lookup"><span data-stu-id="43637-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="43637-103">В этой статье описывается, как импортировать командлеты в сеанс PowerShell с помощью двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="43637-103">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="43637-104">Членами модулей могут быть командлеты, поставщики, функции, переменные, псевдонимы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="43637-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="43637-105">Оснастки могут содержать только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="43637-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="43637-106">Как загружать командлеты с помощью модуля</span><span class="sxs-lookup"><span data-stu-id="43637-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="43637-107">Создайте папку модуля, имя которой совпадает с именем файла сборки, в котором реализуются командлеты.</span><span class="sxs-lookup"><span data-stu-id="43637-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="43637-108">В этой процедуре папка Module создается в `system32` папке Windows.</span><span class="sxs-lookup"><span data-stu-id="43637-108">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="43637-109">Убедитесь, что `PSModulePath` переменная среды содержит путь к новой папке модуля.</span><span class="sxs-lookup"><span data-stu-id="43637-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="43637-110">По умолчанию системная папка уже добавлена в `PSModulePath` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="43637-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="43637-111">Чтобы просмотреть `PSModulePath` , введите: `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="43637-111">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="43637-112">Скопируйте сборку командлета в папку Module.</span><span class="sxs-lookup"><span data-stu-id="43637-112">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="43637-113">Добавьте файл манифеста модуля ( `.psd1` ) в корневую папку модуля.</span><span class="sxs-lookup"><span data-stu-id="43637-113">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="43637-114">PowerShell использует манифест модуля для импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="43637-114">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="43637-115">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="43637-115">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="43637-116">Выполните следующую команду, чтобы добавить командлеты в сеанс:</span><span class="sxs-lookup"><span data-stu-id="43637-116">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="43637-117">Эту процедуру можно использовать для проверки командлетов.</span><span class="sxs-lookup"><span data-stu-id="43637-117">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="43637-118">Он добавляет все командлеты в сборку в сеанс.</span><span class="sxs-lookup"><span data-stu-id="43637-118">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="43637-119">Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="43637-119">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43637-120">См. также</span><span class="sxs-lookup"><span data-stu-id="43637-120">See also</span></span>

[<span data-ttu-id="43637-121">Как написать манифест модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="43637-121">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="43637-122">Импорт модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="43637-122">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="43637-123">Import-Module</span><span class="sxs-lookup"><span data-stu-id="43637-123">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="43637-124">Установка модулей</span><span class="sxs-lookup"><span data-stu-id="43637-124">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="43637-125">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="43637-125">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="43637-126">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43637-126">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
