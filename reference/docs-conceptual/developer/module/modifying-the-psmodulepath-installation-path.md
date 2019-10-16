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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360673"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="24bdd-102">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="24bdd-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="24bdd-103">Переменная среды `PSModulePath` сохраняет пути к расположениям модулей, установленных на диске.</span><span class="sxs-lookup"><span data-stu-id="24bdd-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="24bdd-104">Windows PowerShell использует эту переменную для поиска модулей, когда пользователь не указал полный путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="24bdd-104">Windows PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="24bdd-105">Пути в этой переменной ищутся в том порядке, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="24bdd-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="24bdd-106">При запуске Windows PowerShell `PSModulePath` создается как системная переменная среды со следующим значением по умолчанию: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="24bdd-106">When Windows PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="24bdd-107">Просмотр переменной PSModulePath</span><span class="sxs-lookup"><span data-stu-id="24bdd-107">To view the PSModulePath variable</span></span>

<span data-ttu-id="24bdd-108">Чтобы просмотреть пути, указанные в переменной `PSModulePath`, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24bdd-108">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="24bdd-109">Добавление расположений в переменную PSModulePath</span><span class="sxs-lookup"><span data-stu-id="24bdd-109">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="24bdd-110">Чтобы добавить пути к этой переменной, используйте один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="24bdd-110">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="24bdd-111">Чтобы добавить временное значение, доступное только для текущего сеанса, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24bdd-111">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- <span data-ttu-id="24bdd-112">Чтобы добавить постоянное значение, доступное при каждом открытии сеанса, добавьте следующую команду в профиль Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="24bdd-112">To add a persistent value that is available whenever a session is opened, add the following command to a Windows PowerShell profile:</span></span>

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  <span data-ttu-id="24bdd-113">Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) в библиотеке Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="24bdd-113">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) in the Microsoft TechNet library.</span></span>

- <span data-ttu-id="24bdd-114">Чтобы добавить постоянную переменную в реестр, создайте новую переменную среды пользователя с именем `PSModulePath` с помощью редактора переменных среды в диалоговом окне " **Свойства системы** ".</span><span class="sxs-lookup"><span data-stu-id="24bdd-114">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="24bdd-115">Чтобы добавить постоянную переменную с помощью скрипта, используйте метод **SetEnvironmentVariable** класса Environment.</span><span class="sxs-lookup"><span data-stu-id="24bdd-115">To add a persistent variable by using a script, use the **SetEnvironmentVariable** method on the Environment class.</span></span> <span data-ttu-id="24bdd-116">Например, следующий скрипт добавляет путь "C:\Program Филес\фабрикам\модуле" к значению переменной среды PSModulePath для компьютера.</span><span class="sxs-lookup"><span data-stu-id="24bdd-116">For example, the following script adds the "C:\Program Files\Fabrikam\Module path to the value of the PSModulePath environment variable for the computer.</span></span> <span data-ttu-id="24bdd-117">Чтобы добавить путь к переменной среды пользователя PSModulePath, задайте для целевого объекта значение "User".</span><span class="sxs-lookup"><span data-stu-id="24bdd-117">To add the path to the user PSModulePath environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="24bdd-118">Удаление расположений из PSModulePath</span><span class="sxs-lookup"><span data-stu-id="24bdd-118">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="24bdd-119">Вы можете удалить пути из переменной с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` удалит путь **к:\модулепас** из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="24bdd-119">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="24bdd-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="24bdd-120">See Also</span></span>

[<span data-ttu-id="24bdd-121">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24bdd-121">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
