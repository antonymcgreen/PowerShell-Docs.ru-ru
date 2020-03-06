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
ms.openlocfilehash: b176d8439025ac132962859f79e72ae6f9703e82
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78405034"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="ab3b1-102">Изменение пути установки PSModulePath</span><span class="sxs-lookup"><span data-stu-id="ab3b1-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="ab3b1-103">Переменная среды `PSModulePath` сохраняет пути к расположениям модулей, установленных на диске.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="ab3b1-104">PowerShell использует эту переменную для поиска модулей, когда пользователь не указал полный путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-104">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="ab3b1-105">Пути в этой переменной ищутся в том порядке, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="ab3b1-106">При запуске PowerShell `PSModulePath` создается как системная переменная среды со следующим значением по умолчанию: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` в Windows и `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` в Linux или Mac, а также `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-106">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="ab3b1-107">Заданное пользователем расположение **CurrentUser** — это папка `WindowsPowerShell\Modules`, расположенная в папке **Documents** в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-107">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="ab3b1-108">Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-108">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="ab3b1-109">По умолчанию в Windows 10 это расположение `$HOME\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-109">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="ab3b1-110">Просмотр переменной PSModulePath</span><span class="sxs-lookup"><span data-stu-id="ab3b1-110">To view the PSModulePath variable</span></span>

<span data-ttu-id="ab3b1-111">Чтобы просмотреть пути, указанные в переменной `PSModulePath`, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab3b1-111">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="ab3b1-112">Добавление расположений в переменную PSModulePath</span><span class="sxs-lookup"><span data-stu-id="ab3b1-112">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="ab3b1-113">Чтобы добавить пути к этой переменной, используйте один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-113">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="ab3b1-114">Чтобы добавить временное значение, доступное только для текущего сеанса, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab3b1-114">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="ab3b1-115">Чтобы добавить постоянное значение, доступное при каждом открытии сеанса, добавьте приведенную выше команду в файл профиля PowerShell (`$PROFILE`) ></span><span class="sxs-lookup"><span data-stu-id="ab3b1-115">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="ab3b1-116">Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="ab3b1-116">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="ab3b1-117">Чтобы добавить постоянную переменную в реестр, создайте новую переменную среды пользователя с именем `PSModulePath`, используя редактор переменных среды в диалоговом окне " **Свойства системы** ".</span><span class="sxs-lookup"><span data-stu-id="ab3b1-117">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="ab3b1-118">Чтобы добавить постоянную переменную с помощью скрипта, используйте метод .NET [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable) в классе [System. Environment](https://docs.microsoft.com/dotnet/api/system.environment) .</span><span class="sxs-lookup"><span data-stu-id="ab3b1-118">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](https://docs.microsoft.com/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="ab3b1-119">Например, следующий скрипт добавляет путь `C:\Program Files\Fabrikam\Module` к значению переменной среды `PSModulePath` для компьютера.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-119">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="ab3b1-120">Чтобы добавить путь к пользовательской переменной среды `PSModulePath`, задайте для целевого объекта значение "User".</span><span class="sxs-lookup"><span data-stu-id="ab3b1-120">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="ab3b1-121">Удаление расположений из PSModulePath</span><span class="sxs-lookup"><span data-stu-id="ab3b1-121">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="ab3b1-122">Вы можете удалить пути из переменной с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` удалит путь **к:\модулепас** из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3b1-122">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab3b1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab3b1-123">See Also</span></span>

[<span data-ttu-id="ab3b1-124">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab3b1-124">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="ab3b1-125">about_Modules</span><span class="sxs-lookup"><span data-stu-id="ab3b1-125">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
