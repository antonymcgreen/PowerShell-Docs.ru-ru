---
title: Установка модуля PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: 60ac4bf9089232a9fa879e835e32da53422489fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367073"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="6c038-102">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c038-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="6c038-103">После создания модуля PowerShell, вероятно, потребуется установить модуль в системе, чтобы вы или другие могли его использовать.</span><span class="sxs-lookup"><span data-stu-id="6c038-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="6c038-104">В целом, это состоит из копирования файлов модулей (Internet Explorer,. PSM1 или двоичной сборки, манифеста модуля и других связанных файлов) в каталог на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="6c038-104">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="6c038-105">Для очень маленького проекта это может быть просто копированием и вставлением файлов с помощью проводника Windows на один удаленный компьютер. Однако для более крупных решений может потребоваться более сложный процесс установки.</span><span class="sxs-lookup"><span data-stu-id="6c038-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="6c038-106">Независимо от того, как вы получаете модуль в системе, PowerShell может использовать ряд методов, позволяющих пользователям находить и использовать ваши модули.</span><span class="sxs-lookup"><span data-stu-id="6c038-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="6c038-107">Поэтому основная ошибка установки гарантирует, что PowerShell сможет найти ваш модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-107">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="6c038-108">Дополнительные сведения см. [в разделе Импорт модуля PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="6c038-108">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="6c038-109">Правила установки модулей</span><span class="sxs-lookup"><span data-stu-id="6c038-109">Rules for Installing Modules</span></span>

<span data-ttu-id="6c038-110">Следующие сведения относятся ко всем модулям, включая модули, созданные для собственного использования, модули, получаемые от других сторон, и модули, распространяемые другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6c038-110">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="6c038-111">Установка модулей в PSModulePath</span><span class="sxs-lookup"><span data-stu-id="6c038-111">Install Modules in PSModulePath</span></span>

<span data-ttu-id="6c038-112">Когда это возможно, установите все модули в пути, указанном в переменной среды **PSModulePath** , или добавьте путь к модулю в значение переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="6c038-112">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="6c038-113">Переменная среды **PSModulePath** ($env:P смодулепас) содержит расположение модулей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c038-113">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="6c038-114">Командлеты используют значение этой переменной среды для поиска модулей.</span><span class="sxs-lookup"><span data-stu-id="6c038-114">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="6c038-115">По умолчанию значение переменной среды **PSModulePath** содержит следующие системные и пользовательские каталоги модулей, но можно добавлять и изменять значения.</span><span class="sxs-lookup"><span data-stu-id="6c038-115">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="6c038-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="6c038-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="6c038-117">Это расположение зарезервировано для модулей, поставляемых с Windows.</span><span class="sxs-lookup"><span data-stu-id="6c038-117">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="6c038-118">Не устанавливайте модули в это расположение.</span><span class="sxs-lookup"><span data-stu-id="6c038-118">Do not install modules to this location.</span></span>

- <span data-ttu-id="6c038-119">`$Home\Documents\WindowsPowerShell\Modules` (%Усерпрофиле%\документс\виндовсповершелл\модулес)</span><span class="sxs-lookup"><span data-stu-id="6c038-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="6c038-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%Програмфилес%\виндовсповершелл\модулес)</span><span class="sxs-lookup"><span data-stu-id="6c038-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="6c038-121">Чтобы получить значение переменной среды **PSModulePath** , используйте одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="6c038-121">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="6c038-122">Чтобы добавить путь к модулю в значение переменной среды **PSModulePath** , используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="6c038-122">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="6c038-123">Этот формат использует метод **SetEnvironmentVariable** класса **System. Environment** , чтобы сделать независимым от сеанса изменение переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="6c038-123">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="6c038-124">После добавления пути к **PSModulePath**следует транслировать сообщение окружения об изменении.</span><span class="sxs-lookup"><span data-stu-id="6c038-124">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="6c038-125">Широковещательная рассылка изменений позволяет другим приложениям, таким как оболочка, принимать изменения.</span><span class="sxs-lookup"><span data-stu-id="6c038-125">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="6c038-126">Чтобы выполнить широковещательную рассылку изменений, необходимо, чтобы код установки продукта отправлял сообщение **WM_SETTINGCHANGE** с параметром `lParam`, равным строке "среда".</span><span class="sxs-lookup"><span data-stu-id="6c038-126">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="6c038-127">Не забудьте отправить сообщение после того, как код установки модуля обновил **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="6c038-127">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="6c038-128">Использовать правильное имя каталога модулей</span><span class="sxs-lookup"><span data-stu-id="6c038-128">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="6c038-129">Правильно сформированный модуль — это модуль, хранящийся в каталоге, имя которого совпадает с базовым именем по крайней мере одного файла в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-129">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="6c038-130">Если модуль не имеет правильного формата, Windows PowerShell не распознает его как модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-130">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="6c038-131">"Базовое имя" файла — это имя без расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="6c038-131">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="6c038-132">В правильно оформленном модуле имя каталога, содержащего файлы модулей, должно совпадать с базовым именем по крайней мере одного файла в модуле.</span><span class="sxs-lookup"><span data-stu-id="6c038-132">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="6c038-133">Например, в примере модуля Fabrikam каталог, содержащий файлы модулей, называется Fabrikam, а по крайней мере один файл имеет базовое имя "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="6c038-133">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="6c038-134">В этом случае Fabrikam. PSD1 и Fabrikam. DLL имеют базовое имя "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="6c038-134">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="6c038-135">Воздействие неправильной установки</span><span class="sxs-lookup"><span data-stu-id="6c038-135">Effect of Incorrect Installation</span></span>

<span data-ttu-id="6c038-136">Если модуль не имеет правильного формата и его расположение не включено в значение переменной среды **PSModulePath** , основные функции обнаружения Windows PowerShell, такие как следующие, не работают.</span><span class="sxs-lookup"><span data-stu-id="6c038-136">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="6c038-137">Функция автоматической загрузки модуля не может автоматически импортировать модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-137">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="6c038-138">Параметр `ListAvailable` командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) не может найти модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-138">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="6c038-139">Командлету [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) не удается найти модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-139">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="6c038-140">Чтобы импортировать модуль, необходимо указать полный путь к файлу корневого модуля или файла манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-140">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="6c038-141">Дополнительные функции, например следующие, не работают, если модуль не импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="6c038-141">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="6c038-142">В модулях с правильным форматом в переменной среды **PSModulePath** эти функции работают даже в том случае, если модуль не импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="6c038-142">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="6c038-143">Командлету [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) не удается найти команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="6c038-143">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="6c038-144">Командлеты [Update — Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) не могут обновить или сохранить справку для модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-144">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="6c038-145">Командлету " [Показать-команда](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) " не удается найти и отобразить команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="6c038-145">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="6c038-146">Команды в модуле отсутствуют в окне `Show-Command` в интегрированной среде сценариев Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="6c038-146">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="6c038-147">Место установки модулей</span><span class="sxs-lookup"><span data-stu-id="6c038-147">Where to Install Modules</span></span>

<span data-ttu-id="6c038-148">В этом разделе описывается, где в файловой системе устанавливаются модули Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c038-148">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="6c038-149">Расположение зависит от того, как используется модуль.</span><span class="sxs-lookup"><span data-stu-id="6c038-149">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="6c038-150">Установка модулей для определенного пользователя</span><span class="sxs-lookup"><span data-stu-id="6c038-150">Installing Modules for a Specific User</span></span>

<span data-ttu-id="6c038-151">Если вы создаете собственный модуль или получаете модуль от другой стороны, например веб-сайт сообщества Windows PowerShell, и вам требуется, чтобы модуль был доступен только для вашей учетной записи пользователя, установите модуль в каталоге модулей для конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6c038-151">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="6c038-152">Каталог пользовательских модулей добавляется к значению переменной среды **PSModulePath** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6c038-152">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="6c038-153">Установка модулей для всех пользователей в программных файлах</span><span class="sxs-lookup"><span data-stu-id="6c038-153">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="6c038-154">Если требуется, чтобы модуль был доступен для всех учетных записей пользователей на компьютере, установите модуль в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="6c038-154">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="6c038-155">Расположение программных файлов добавляется в значение переменной среды PSModulePath по умолчанию в Windows PowerShell 4,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="6c038-155">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="6c038-156">Для более ранних версий Windows PowerShell можно вручную создать расположение программных файлов ((%Програмфилес%\виндовсповершелл\модулес) и добавить этот путь в переменную среды PSModulePath, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="6c038-156">For earlier versions of Windows PowerShell, you can manually create the Program Files location ((%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="6c038-157">Установка модулей в каталоге продукта</span><span class="sxs-lookup"><span data-stu-id="6c038-157">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="6c038-158">Если вы распространяете модуль другим сторонам, используйте расположение программных файлов по умолчанию, описанное выше, или создайте собственный подкаталог, относящийся к конкретной компании или продукт, в каталоге% ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="6c038-158">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="6c038-159">Например, технологии Fabrikam, вымышленная компания, поставляют модуль Windows PowerShell для своего продукта Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="6c038-159">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="6c038-160">Установщик модуля создает подкаталог modules в подкаталоге продукта Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="6c038-160">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="6c038-161">Чтобы включить функции обнаружения модулей Windows PowerShell для поиска модуля Fabrikam, Установщик модуля Fabrikam добавляет расположение модуля в значение переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="6c038-161">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="6c038-162">Установка модулей в каталоге общих файлов</span><span class="sxs-lookup"><span data-stu-id="6c038-162">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="6c038-163">Если модуль используется несколькими компонентами продукта или несколькими версиями продукта, установите модуль в подкаталог, зависящий от модуля, в подкаталоге%ProgramFiles%\Common Филес\модулес.</span><span class="sxs-lookup"><span data-stu-id="6c038-163">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="6c038-164">В следующем примере модуль Fabrikam устанавливается в подкаталог Fabrikam подкаталога `%ProgramFiles%\Common Files\Modules`.</span><span class="sxs-lookup"><span data-stu-id="6c038-164">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="6c038-165">Обратите внимание, что каждый модуль находится в отдельном подкаталоге в подкаталоге modules.</span><span class="sxs-lookup"><span data-stu-id="6c038-165">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="6c038-166">Затем установщик гарантирует, что значение переменной среды **PSModulePath** включает путь к подкаталогу Common Files modules.</span><span class="sxs-lookup"><span data-stu-id="6c038-166">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="6c038-167">Установка нескольких версий модуля</span><span class="sxs-lookup"><span data-stu-id="6c038-167">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="6c038-168">Чтобы установить несколько версий одного модуля, выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="6c038-168">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="6c038-169">Создайте каталог для каждой версии модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-169">Create a directory for each version of the module.</span></span> <span data-ttu-id="6c038-170">Включить номер версии в имя каталога.</span><span class="sxs-lookup"><span data-stu-id="6c038-170">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="6c038-171">Создайте манифест модуля для каждой версии модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-171">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="6c038-172">В поле **значение ключа "** в манифесте" введите номер версии модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-172">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="6c038-173">Сохраните файл манифеста (. PSD1) в каталоге, зависящем от версии, для модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-173">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="6c038-174">Добавьте путь к корневой папке модуля в значение переменной среды **PSModulePath** , как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6c038-174">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="6c038-175">Чтобы импортировать определенную версию модуля, конечный пользователь может использовать параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .</span><span class="sxs-lookup"><span data-stu-id="6c038-175">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="6c038-176">Например, если модуль Fabrikam доступен в версиях 8,0 и 9,0, структура каталогов модуля Fabrikam может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6c038-176">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

<span data-ttu-id="6c038-177">Установщик добавляет оба пути к модулю в значение переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="6c038-177">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="6c038-178">После выполнения этих действий параметр **ListAvailable** командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) получает оба модуля Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6c038-178">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="6c038-179">Чтобы импортировать определенный модуль, используйте параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .</span><span class="sxs-lookup"><span data-stu-id="6c038-179">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="6c038-180">Если оба модуля импортируются в один сеанс, а модули содержат командлеты с одинаковыми именами, командлеты, импортируемые последними, вступают в силу в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="6c038-180">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="6c038-181">Обработка конфликтов имен команд</span><span class="sxs-lookup"><span data-stu-id="6c038-181">Handling Command Name Conflicts</span></span>

<span data-ttu-id="6c038-182">Конфликты имен команд могут возникать, когда команды, экспортируемые модулем, имеют те же имена, что и команды в сеансе пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c038-182">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="6c038-183">Если сеанс содержит две команды с одинаковыми именами, Windows PowerShell выполняет тип команды, имеющий приоритет.</span><span class="sxs-lookup"><span data-stu-id="6c038-183">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="6c038-184">Если сеанс содержит две команды с одинаковым именем и одним и тем же типом, Windows PowerShell выполняет команду, которая была добавлена в сеанс в последнее время.</span><span class="sxs-lookup"><span data-stu-id="6c038-184">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="6c038-185">Чтобы выполнить команду, которая не выполняется по умолчанию, пользователи могут указать имя модуля в качестве имени команды.</span><span class="sxs-lookup"><span data-stu-id="6c038-185">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="6c038-186">Например, если сеанс содержит функцию `Get-Date` и командлет `Get-Date`, Windows PowerShell по умолчанию выполняет эту функцию.</span><span class="sxs-lookup"><span data-stu-id="6c038-186">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="6c038-187">Чтобы выполнить командлет, перед командой введите имя модуля, например:</span><span class="sxs-lookup"><span data-stu-id="6c038-187">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="6c038-188">Чтобы предотвратить конфликты имен, авторы модулей могут использовать ключ **DefaultCommandPrefix** в манифесте модуля, чтобы указать префикс существительное для всех команд, экспортируемых из модуля.</span><span class="sxs-lookup"><span data-stu-id="6c038-188">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="6c038-189">Для использования альтернативного префикса пользователи могут использовать параметр **prefix** командлета `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="6c038-189">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="6c038-190">Значение параметра **prefix** имеет приоритет над значением ключа **DefaultCommandPrefix** .</span><span class="sxs-lookup"><span data-stu-id="6c038-190">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c038-191">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c038-191">See Also</span></span>

[<span data-ttu-id="6c038-192">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="6c038-192">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="6c038-193">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c038-193">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
