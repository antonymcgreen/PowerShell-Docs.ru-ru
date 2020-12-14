---
ms.date: 09/13/2016
ms.topic: reference
title: Установка модуля PowerShell
description: Установка модуля PowerShell
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645331"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="3325c-103">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="3325c-103">Installing a PowerShell Module</span></span>

<span data-ttu-id="3325c-104">После создания модуля PowerShell вы, вероятно, захотите установить модуль в системе, чтобы его могли использовать не только вы, но и другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="3325c-104">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="3325c-105">В целом, этот процесс включает копирование файлов модулей (файлы PSM1 или двоичной сборки, манифеста модуля и другие связанные файлы) в каталог на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3325c-105">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="3325c-106">Для очень маленького проекта это может быть просто копирование и вставка файлов с помощью проводника Windows на один удаленный компьютер. Но для более крупных решений может потребоваться более сложный процесс установки.</span><span class="sxs-lookup"><span data-stu-id="3325c-106">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="3325c-107">Независимо от того, как вы устанавливаете модуль в системе, PowerShell поддерживает ряд методов, с помощью которых пользователи могут находить и использовать ваши модули.</span><span class="sxs-lookup"><span data-stu-id="3325c-107">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="3325c-108">Следовательно, основная задача установки — сделать так, чтобы ваш модуль был доступным для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3325c-108">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="3325c-109">Дополнительные сведения см. в статье [Импорт модуля PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="3325c-109">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="3325c-110">Правила установки модулей</span><span class="sxs-lookup"><span data-stu-id="3325c-110">Rules for Installing Modules</span></span>

<span data-ttu-id="3325c-111">Следующие сведения относятся ко всем модулям, включая модули, созданные для собственного использования, получаемые от других сторон и предоставляемые другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="3325c-111">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="3325c-112">Установка модулей в PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3325c-112">Install Modules in PSModulePath</span></span>

<span data-ttu-id="3325c-113">По возможности устанавливайте все модули по пути, указанному в переменной среды **PSModulePath**, или добавьте путь к модулю в значение переменной среды **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="3325c-113">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="3325c-114">Переменная среды **PSModulePath** ($Env:PSModulePath) содержит сведения о расположении модулей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3325c-114">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="3325c-115">Командлеты используют значение этой переменной среды для поиска модулей.</span><span class="sxs-lookup"><span data-stu-id="3325c-115">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="3325c-116">По умолчанию значение переменной среды **PSModulePath** содержит следующие системные и пользовательские каталоги модулей, но вы можете добавлять и изменять это значение.</span><span class="sxs-lookup"><span data-stu-id="3325c-116">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="3325c-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="3325c-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="3325c-118">Это расположение зарезервировано для модулей, поставляемых с Windows.</span><span class="sxs-lookup"><span data-stu-id="3325c-118">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="3325c-119">Не устанавливайте модули в это расположение.</span><span class="sxs-lookup"><span data-stu-id="3325c-119">Do not install modules to this location.</span></span>

- <span data-ttu-id="3325c-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="3325c-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="3325c-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="3325c-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="3325c-122">Чтобы получить значение переменной среды **PSModulePath**, используйте одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="3325c-122">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="3325c-123">Чтобы добавить путь к модулю в значение переменной среды **PSModulePath**, используйте следующий формат команды.</span><span class="sxs-lookup"><span data-stu-id="3325c-123">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="3325c-124">В этом формате используется метод **SetEnvironmentVariable** класса **System.Environment**, чтобы сделать изменение переменной среды **PSModulePath** независимым от сеанса.</span><span class="sxs-lookup"><span data-stu-id="3325c-124">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="3325c-125">После добавления пути в **PSModulePath** выполните рассылку сообщения окружения об изменении.</span><span class="sxs-lookup"><span data-stu-id="3325c-125">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="3325c-126">Так другие приложения, например оболочка, смогут поддерживать эти изменения.</span><span class="sxs-lookup"><span data-stu-id="3325c-126">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="3325c-127">Для этого код установки продукта должен отправить сообщение **WM_SETTINGCHANGE** с параметром `lParam`, для которого задана строка Environment.</span><span class="sxs-lookup"><span data-stu-id="3325c-127">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="3325c-128">Не забудьте отправить сообщение после того, как код установки модуля обновит **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="3325c-128">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="3325c-129">Использование правильного имени каталога модулей</span><span class="sxs-lookup"><span data-stu-id="3325c-129">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="3325c-130">Модуль с правильным форматом — это модуль, хранящийся в каталоге, имя которого совпадает с базовым именем хотя бы одного файла в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-130">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="3325c-131">Если формат модуля неправильный, Windows PowerShell не распознает его как модуль.</span><span class="sxs-lookup"><span data-stu-id="3325c-131">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="3325c-132">Базовое имя файла — это имя файла без расширения.</span><span class="sxs-lookup"><span data-stu-id="3325c-132">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="3325c-133">В модуле с правильным форматом имя каталога, содержащего файлы модулей, должно совпадать с базовым именем хотя бы одного файла в модуле.</span><span class="sxs-lookup"><span data-stu-id="3325c-133">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="3325c-134">Например, в примере модуля Fabrikam каталог, содержащий файлы модулей, называется Fabrikam, и хотя бы один файл имеет базовое имя Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="3325c-134">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="3325c-135">В этом случае и Fabrikam.psd1, и Fabrikam.dll имеют базовое имя Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="3325c-135">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="3325c-136">Результат неправильной установки</span><span class="sxs-lookup"><span data-stu-id="3325c-136">Effect of Incorrect Installation</span></span>

<span data-ttu-id="3325c-137">Если модуль имеет неправильный формат и его расположение не включено в значение переменной среды **PSModulePath**, основные функции обнаружения Windows PowerShell, описанные ниже, не будут работать.</span><span class="sxs-lookup"><span data-stu-id="3325c-137">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="3325c-138">Функция автоматической загрузки модуля не сможет автоматически импортировать модуль.</span><span class="sxs-lookup"><span data-stu-id="3325c-138">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="3325c-139">Параметр `ListAvailable` командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) не сможет найти модуль.</span><span class="sxs-lookup"><span data-stu-id="3325c-139">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="3325c-140">Командлет [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) не сможет найти модуль.</span><span class="sxs-lookup"><span data-stu-id="3325c-140">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="3325c-141">Чтобы импортировать модуль, необходимо указать полный путь к файлу корневого модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-141">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="3325c-142">Дополнительные функции, описанные ниже, не будут работать, если модуль не импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="3325c-142">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="3325c-143">В модулях с правильным форматом в переменной среды **PSModulePath** эти функции будут работать, даже если модуль не импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="3325c-143">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="3325c-144">Командлет [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) не сможет найти команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="3325c-144">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="3325c-145">Командлеты [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) не смогут обновить или сохранить справку для модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-145">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="3325c-146">Командлет [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) не сможет найти и отобразить команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="3325c-146">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="3325c-147">Команды в модуле будут отсутствовать в окне `Show-Command` в интегрированной среде скриптов Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="3325c-147">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="3325c-148">Расположение для установки модулей</span><span class="sxs-lookup"><span data-stu-id="3325c-148">Where to Install Modules</span></span>

<span data-ttu-id="3325c-149">В этом разделе описывается, где в файловой системе устанавливаются модули Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3325c-149">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="3325c-150">Расположение зависит от того, как используется модуль.</span><span class="sxs-lookup"><span data-stu-id="3325c-150">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="3325c-151">Установка модулей для определенного пользователя</span><span class="sxs-lookup"><span data-stu-id="3325c-151">Installing Modules for a Specific User</span></span>

<span data-ttu-id="3325c-152">Если вы создаете собственный модуль или получаете модуль от другой стороны, например с веб-сайта сообщества Windows PowerShell, и вам нужно, чтобы модуль был доступен только для вашей учетной записи пользователя, установите модуль в пользовательском каталоге модулей.</span><span class="sxs-lookup"><span data-stu-id="3325c-152">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="3325c-153">Этот каталог добавляется в значение переменной среды **PSModulePath** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3325c-153">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="3325c-154">Установка модулей для всех пользователей в программных файлах</span><span class="sxs-lookup"><span data-stu-id="3325c-154">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="3325c-155">Если вам нужно, чтобы модуль был доступен для всех учетных записей пользователей на компьютере, установите модуль в папку с программными файлами.</span><span class="sxs-lookup"><span data-stu-id="3325c-155">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="3325c-156">Это расположение добавляется в значение переменной среды PSModulePath по умолчанию в Windows PowerShell 4.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="3325c-156">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="3325c-157">Для более ранних версий Windows PowerShell можно вручную создать расположение программных файлов (%ProgramFiles%\WindowsPowerShell\Modules) и добавить этот путь в переменную среды PSModulePath, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="3325c-157">For earlier versions of Windows PowerShell, you can manually create the Program Files location (%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="3325c-158">Установка модулей в каталоге продукта</span><span class="sxs-lookup"><span data-stu-id="3325c-158">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="3325c-159">Если вы предоставляете модуль другим сторонам, используйте каталог с программными файлами по умолчанию, как описано выше, или создайте собственный подкаталог для компании или продукта в каталоге %ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="3325c-159">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="3325c-160">Например вымышленная компания Fabrikam Technologies предоставляет модуль Windows PowerShell для своего продукта Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="3325c-160">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="3325c-161">Установщик модуля создает подкаталог Modules в подкаталоге продукта Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="3325c-161">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="3325c-162">Чтобы включить функции обнаружения модулей Windows PowerShell для поиска модуля Fabrikam, установщик модуля Fabrikam добавляет расположение модуля в значение переменной среды **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="3325c-162">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="3325c-163">Установка модулей в каталоге с общими файлами</span><span class="sxs-lookup"><span data-stu-id="3325c-163">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="3325c-164">Если модуль используется несколькими компонентами или версиями продукта, установите модуль в подкаталог для модуля в подкаталоге %ProgramFiles%\Common Files\Modules.</span><span class="sxs-lookup"><span data-stu-id="3325c-164">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="3325c-165">В следующем примере модуль Fabrikam устанавливается в подкаталог Fabrikam в подкаталоге `%ProgramFiles%\Common Files\Modules`.</span><span class="sxs-lookup"><span data-stu-id="3325c-165">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="3325c-166">Обратите внимание, что каждый модуль находится в отдельном подкаталоге в подкаталоге Modules.</span><span class="sxs-lookup"><span data-stu-id="3325c-166">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="3325c-167">Затем установщик проверяет, что значение переменной среды **PSModulePath** содержит путь к подкаталогу модуля с общими файлами.</span><span class="sxs-lookup"><span data-stu-id="3325c-167">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

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

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="3325c-168">Установка нескольких версий модуля</span><span class="sxs-lookup"><span data-stu-id="3325c-168">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="3325c-169">Чтобы установить несколько версий одного модуля, выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="3325c-169">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="3325c-170">Создайте каталог для каждой версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-170">Create a directory for each version of the module.</span></span> <span data-ttu-id="3325c-171">Включите номер версии в имя каталога.</span><span class="sxs-lookup"><span data-stu-id="3325c-171">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="3325c-172">Создайте манифест модуля для каждой версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-172">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="3325c-173">В качестве значения ключа **ModuleVersion** в манифесте укажите номер версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-173">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="3325c-174">Сохраните файл манифеста (.psd1) в каталоге для версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-174">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="3325c-175">Добавьте путь к корневой папке модуля в значение переменной среды **PSModulePath**, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="3325c-175">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="3325c-176">Чтобы импортировать определенную версию модуля, пользователь может использовать параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="3325c-176">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="3325c-177">Например, если модуль Fabrikam доступен в версиях 8.0 и 9.0, структура каталогов модуля Fabrikam может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3325c-177">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

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

<span data-ttu-id="3325c-178">Установщик добавляет оба пути к модулю в значение переменной среды **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="3325c-178">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="3325c-179">После выполнения этих действий параметр **ListAvailable** командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) получает оба модуля Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="3325c-179">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="3325c-180">Чтобы импортировать определенный модуль, используйте параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="3325c-180">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="3325c-181">Если оба модуля, которые содержат командлеты с одинаковыми именами, импортируются в один сеанс, в этом сеансе будут доступными командлеты, импортированные последними.</span><span class="sxs-lookup"><span data-stu-id="3325c-181">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="3325c-182">Обработка конфликтов имен команд</span><span class="sxs-lookup"><span data-stu-id="3325c-182">Handling Command Name Conflicts</span></span>

<span data-ttu-id="3325c-183">Конфликты имен команд могут возникать, когда команды, экспортируемые модулем, имеют те же имена, что и команды в сеансе пользователя.</span><span class="sxs-lookup"><span data-stu-id="3325c-183">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="3325c-184">Если сеанс содержит две команды с одинаковым именем, Windows PowerShell выполняет команду согласно приоритету по типу.</span><span class="sxs-lookup"><span data-stu-id="3325c-184">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="3325c-185">Если сеанс содержит две команды с одинаковыми именем и типом, Windows PowerShell выполняет команду, которая была добавлена в сеанс последней.</span><span class="sxs-lookup"><span data-stu-id="3325c-185">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="3325c-186">Чтобы выполнить команду, которая не выполняется по умолчанию, пользователи могут определить ее имя, используя имя модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-186">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="3325c-187">Например, если сеанс содержит функцию `Get-Date` и командлет `Get-Date`, Windows PowerShell по умолчанию выполняет эту функцию.</span><span class="sxs-lookup"><span data-stu-id="3325c-187">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="3325c-188">Чтобы выполнить командлет, укажите перед командой имя модуля, например:</span><span class="sxs-lookup"><span data-stu-id="3325c-188">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="3325c-189">Чтобы предотвратить конфликты имен, авторы модулей могут использовать ключ **DefaultCommandPrefix** в манифесте модуля, чтобы указать префикс существительного для всех команд, экспортируемых из модуля.</span><span class="sxs-lookup"><span data-stu-id="3325c-189">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="3325c-190">Чтобы применить альтернативный префикс, пользователи могут использовать параметр **Prefix** командлета `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="3325c-190">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="3325c-191">Значение параметра **Prefix** имеет приоритет над значением ключа **DefaultCommandPrefix**.</span><span class="sxs-lookup"><span data-stu-id="3325c-191">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="3325c-192">См. также:</span><span class="sxs-lookup"><span data-stu-id="3325c-192">See Also</span></span>

[<span data-ttu-id="3325c-193">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="3325c-193">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="3325c-194">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3325c-194">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
