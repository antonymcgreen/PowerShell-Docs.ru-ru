---
title: Изменение пути установки PSModulePath | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082215"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="3d456-102">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3d456-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="3d456-103">`PSModulePath` Переменной среды сохраняет пути для расположения модулей, установленных на диске.</span><span class="sxs-lookup"><span data-stu-id="3d456-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="3d456-104">Windows PowerShell использует эту переменную для поиска модулей, когда пользователь не указывает полный путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="3d456-104">Windows PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="3d456-105">Поиск путей в этой переменной выполняется в порядке, в котором они появляются.</span><span class="sxs-lookup"><span data-stu-id="3d456-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="3d456-106">При запуске Windows PowerShell, `PSModulePath` создается как системную переменную среды со следующим значением по умолчанию: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="3d456-106">When Windows PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="3d456-107">Чтобы просмотреть переменной PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3d456-107">To view the PSModulePath variable</span></span>

<span data-ttu-id="3d456-108">Чтобы просмотреть пути, указанные в `PSModulePath` переменной, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d456-108">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="3d456-109">Чтобы добавить расположения в переменную PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3d456-109">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="3d456-110">Чтобы добавить пути к этой переменной, используйте один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="3d456-110">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="3d456-111">Чтобы добавить временное значение, которое доступно только для текущего сеанса, выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="3d456-111">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- <span data-ttu-id="3d456-112">Чтобы добавить постоянное значение, которое доступно каждый раз, когда открывается сеанс, добавьте следующую команду в профиль Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d456-112">To add a persistent value that is available whenever a session is opened, add the following command to a Windows PowerShell profile:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  <span data-ttu-id="3d456-113">Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) в библиотеке Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="3d456-113">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) in the Microsoft TechNet library.</span></span>

- <span data-ttu-id="3d456-114">Чтобы добавить переменную постоянных в реестр, создайте новую переменную среды пользователя с именем `PSModulePath` с помощью редактора переменные среды в **системные свойства** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3d456-114">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="3d456-115">Чтобы добавить постоянный переменной с помощью сценария, используйте **SetEnvironmentVariable** метод к классу среды.</span><span class="sxs-lookup"><span data-stu-id="3d456-115">To add a persistent variable by using a script, use the **SetEnvironmentVariable** method on the Environment class.</span></span> <span data-ttu-id="3d456-116">Например следующий сценарий добавляет «C:\Program Files\Fabrikam\Module путь к значению переменной среды PSModulePath для компьютера.</span><span class="sxs-lookup"><span data-stu-id="3d456-116">For example, the following script adds the "C:\Program Files\Fabrikam\Module path to the value of the PSModulePath environment variable for the computer.</span></span> <span data-ttu-id="3d456-117">Чтобы добавить путь в переменной среды PSModulePath пользователя, задайте целевой объект «User».</span><span class="sxs-lookup"><span data-stu-id="3d456-117">To add the path to the user PSModulePath environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="3d456-118">Для удаления расположений из PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3d456-118">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="3d456-119">Можно удалить пути из переменной, с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` приведет к удалению **c:\ModulePath** пути из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d456-119">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d456-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3d456-120">See Also</span></span>

[<span data-ttu-id="3d456-121">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d456-121">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
