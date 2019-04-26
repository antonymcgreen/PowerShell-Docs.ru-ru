---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: c007bb11324e10ffd100797dccd9e6ab0d09a73e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067983"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="3e2d1-102">Импорт командлетов с помощью модулей</span><span class="sxs-lookup"><span data-stu-id="3e2d1-102">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="3e2d1-103">В этом разделе описывается, как импортировать командлеты в сеанс Windows PowerShell с помощью двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-103">This topic describes how to import cmdlets to a Windows PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2d1-104">Модули можно входят командлеты, поставщики, функции, переменные, псевдонимы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-104">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="3e2d1-105">Оснастки может содержать только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-105">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="3e2d1-106">Как загрузить командлеты с помощью модуля</span><span class="sxs-lookup"><span data-stu-id="3e2d1-106">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="3e2d1-107">Создайте папку модуля с тем же именем в качестве файла сборки, в котором реализованы командлеты.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-107">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="3e2d1-108">В этой процедуре вы создадите в папке модуля `system32` папки.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-108">In this procedure, the module folder is created in the `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

2. <span data-ttu-id="3e2d1-109">Убедитесь, что `PSModulePath` переменная среды включает путь к папке нового модуля.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-109">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="3e2d1-110">По умолчанию папке системы уже добавлен `PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-110">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span>

3. <span data-ttu-id="3e2d1-111">Скопируйте командлет сборки в папке модуля.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-111">Copy the cmdlet assembly into the module folder.</span></span>

4. <span data-ttu-id="3e2d1-112">Выполните следующую команду, чтобы добавить командлеты к сеансу:</span><span class="sxs-lookup"><span data-stu-id="3e2d1-112">Run the following command to add the cmdlets to the session:</span></span>

   `import-module [Module_Name]`

   <span data-ttu-id="3e2d1-113">Эту процедуру можно использовать для тестирования командлетов.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-113">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="3e2d1-114">Он добавляет все командлеты в сборке в сеанс.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-114">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="3e2d1-115">Дополнительные сведения о модулях различных типов модулей, различные способы загрузки модулей и как ограничить элементы модуля, которые экспортируются, см. в разделе [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="3e2d1-115">For more information about modules, the different types of modules, the different ways to load modules, and how to restrict the elements of a module that are exported, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3e2d1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3e2d1-116">See Also</span></span>

[<span data-ttu-id="3e2d1-117">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e2d1-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="3e2d1-118">Установка модулей</span><span class="sxs-lookup"><span data-stu-id="3e2d1-118">Installing Modules</span></span>](../module/installing-a-powershell-module.md)