---
title: Создание справки по модулям PowerShell
ms.date: 04/10/2020
ms.openlocfilehash: 496b7e6cadff4d2db15b6452e9d38efcdf1739ec
ms.sourcegitcommit: 8f55c0157280afa4598fe385a706faf330e723a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2020
ms.locfileid: "81219665"
---
# <a name="writing-help-for-powershell-modules"></a><span data-ttu-id="d3460-102">Создание справки по модулям PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3460-102">Writing Help for PowerShell Modules</span></span>

<span data-ttu-id="d3460-103">Модули PowerShell могут включать разделы справки о модуле и о членах модуля, таких как командлеты, поставщики, функции и скрипты.</span><span class="sxs-lookup"><span data-stu-id="d3460-103">PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="d3460-104">`Get-Help` Командлет выводит разделы справки по модулям в том же формате, в котором отображается справка для других элементов PowerShell, а пользователи `Get-Help` используют стандартные команды для получения разделов справки.</span><span class="sxs-lookup"><span data-stu-id="d3460-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="d3460-105">В этом документе описывается формат и правильное размещение разделов справки по модулям, а также приводятся рекомендации по использованию содержимого справки модуля.</span><span class="sxs-lookup"><span data-stu-id="d3460-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="d3460-106">Типы справки по модулям</span><span class="sxs-lookup"><span data-stu-id="d3460-106">Types of Module Help</span></span>

<span data-ttu-id="d3460-107">Модуль может включать следующие типы справки.</span><span class="sxs-lookup"><span data-stu-id="d3460-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="d3460-108">**Справка по командлетам**.</span><span class="sxs-lookup"><span data-stu-id="d3460-108">**Cmdlet Help**.</span></span> <span data-ttu-id="d3460-109">Разделы справки, описывающие командлеты в модуле, — это XML-файлы, использующие схему справки по командам.</span><span class="sxs-lookup"><span data-stu-id="d3460-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="d3460-110">**Справка поставщика**.</span><span class="sxs-lookup"><span data-stu-id="d3460-110">**Provider Help**.</span></span> <span data-ttu-id="d3460-111">Разделы справки, в которых описываются поставщики в модуле, — это XML-файлы, использующие схему справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="d3460-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="d3460-112">**Справка по функциям**.</span><span class="sxs-lookup"><span data-stu-id="d3460-112">**Function Help**.</span></span> <span data-ttu-id="d3460-113">Разделы справки, описывающие функции в модуле, могут быть XML-файлами, которые используют схему справки команды или разделы справки на основе комментариев в функции, а также скрипт или модуль скрипта.</span><span class="sxs-lookup"><span data-stu-id="d3460-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="d3460-114">**Справка по скрипту**.</span><span class="sxs-lookup"><span data-stu-id="d3460-114">**Script Help**.</span></span> <span data-ttu-id="d3460-115">Разделы справки, описывающие скрипты в модуле, могут быть XML-файлами, которые используют схему справки команды или разделы справки на основе комментариев в модуле script или script.</span><span class="sxs-lookup"><span data-stu-id="d3460-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="d3460-116">**Концептуальная Справка ("о программе")**.</span><span class="sxs-lookup"><span data-stu-id="d3460-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="d3460-117">Концептуальный раздел справки ("About") можно использовать для описания модуля и его элементов, а также для объяснения того, как эти элементы можно использовать вместе для выполнения задач.</span><span class="sxs-lookup"><span data-stu-id="d3460-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span>
  <span data-ttu-id="d3460-118">Основные разделы справки — это текстовые файлы с кодировкой Юникод (UTF-8).</span><span class="sxs-lookup"><span data-stu-id="d3460-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="d3460-119">Имя файла должно иметь `about_<name>.help.txt` формат, например. `about_MyModule.help.txt`</span><span class="sxs-lookup"><span data-stu-id="d3460-119">The file name must use the `about_<name>.help.txt` format, such as `about_MyModule.help.txt`.</span></span> <span data-ttu-id="d3460-120">По умолчанию PowerShell включает более 100 этих концептуальных разделов справки и форматирует их, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d3460-120">By default, PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

  ```
  TOPIC
      about_<subject or module name>

  SHORT DESCRIPTION
      A short, one-line description of the topic contents.

  LONG DESCRIPTION
      A detailed, full description of the subject or purpose of the module.

  EXAMPLES
      Examples of how to use the module or how the subject feature works in practice.

  KEYWORDS
      Terms or titles on which you might expect your users to search for the information in this topic.

  SEE ALSO
      Text-only references for further reading. Hyperlinks cannot work in the PowerShell console.

  ```

<span data-ttu-id="d3460-121">Все файлы схемы можно найти в `$PSHOME\Schemas\PSMaml` папке.</span><span class="sxs-lookup"><span data-stu-id="d3460-121">All of the schema files can be found in the `$PSHOME\Schemas\PSMaml` folder.</span></span>

## <a name="placement-of-module-help"></a><span data-ttu-id="d3460-122">Размещение справки по модулю</span><span class="sxs-lookup"><span data-stu-id="d3460-122">Placement of Module Help</span></span>

<span data-ttu-id="d3460-123">`Get-Help` Командлет ищет файлы разделов справки по модулям в подкаталогах, зависящих от языка, в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="d3460-123">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="d3460-124">Например, на следующей схеме структуры каталогов показано расположение разделов справки для модуля Самплемодуле.</span><span class="sxs-lookup"><span data-stu-id="d3460-124">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

```
<ModulePath>
         \SampleModule
               \<en-US>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml
               \<fr-FR>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml

```

> [!NOTE]
> <span data-ttu-id="d3460-125">В `<ModulePath>` этом примере заполнитель представляет один из путей в `PSModulePath` переменной среды, например `$HOME\Documents\Modules`, `$PSHOME\Modules`, или пользовательский путь, указываемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="d3460-125">In the example, the `<ModulePath>` placeholder represents one of the paths in the `PSModulePath` environment variable, such as `$HOME\Documents\Modules`, `$PSHOME\Modules`, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="d3460-126">Получение справки по модулю</span><span class="sxs-lookup"><span data-stu-id="d3460-126">Getting Module Help</span></span>

<span data-ttu-id="d3460-127">Когда пользователь импортирует модуль в сеанс, разделы справки для этого модуля импортируются в сеанс вместе с модулем.</span><span class="sxs-lookup"><span data-stu-id="d3460-127">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="d3460-128">Файлы разделов справки можно вывести в значении ключа FileList в манифесте модуля, однако этот `Export-ModuleMember` командлет не влияет на разделы справки.</span><span class="sxs-lookup"><span data-stu-id="d3460-128">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="d3460-129">Разделы справки по модулям можно предоставить на разных языках.</span><span class="sxs-lookup"><span data-stu-id="d3460-129">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="d3460-130">`Get-Help` Командлет автоматически отображает разделы справки по модулю на языке, указанном для текущего пользователя в разделе региональные и языковые параметры панели управления.</span><span class="sxs-lookup"><span data-stu-id="d3460-130">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="d3460-131">В Windows Vista и более поздних версиях Windows `Get-Help` ищет разделы справки в подкаталогах, относящихся к конкретному языку каталога модуля, в соответствии со стандартами переключения языка, установленными для Windows.</span><span class="sxs-lookup"><span data-stu-id="d3460-131">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="d3460-132">Начиная с PowerShell 3,0, выполнение `Get-Help` команды для командлета или функции запускает автоматический импорт модуля.</span><span class="sxs-lookup"><span data-stu-id="d3460-132">Beginning in PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="d3460-133">`Get-Help` Командлет немедленно отображает содержимое разделов справки в модуле.</span><span class="sxs-lookup"><span data-stu-id="d3460-133">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="d3460-134">Если модуль не содержит разделов справки и разделов справки для команд в модуле на компьютере пользователя, `Get-Help` отображается автоматически созданная Справка.</span><span class="sxs-lookup"><span data-stu-id="d3460-134">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="d3460-135">Автоматически созданная Справка включает синтаксис команды, параметры, типы входных и выходных данных, но не содержит описания.</span><span class="sxs-lookup"><span data-stu-id="d3460-135">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="d3460-136">Автоматически созданная Справка содержит текст, указывающий пользователю на попытку использовать `Update-Help` командлет для загрузки справки по команде из Интернета или общей папки.</span><span class="sxs-lookup"><span data-stu-id="d3460-136">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="d3460-137">Также рекомендуется использовать параметр **Online** `Get-Help` командлета для получения интерактивной версии раздела справки.</span><span class="sxs-lookup"><span data-stu-id="d3460-137">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="d3460-138">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="d3460-138">Supporting Updatable Help</span></span>

<span data-ttu-id="d3460-139">Пользователи PowerShell 3,0 и более поздних версий PowerShell могут загружать и устанавливать обновленные файлы справки для модуля из Интернета или из локальной общей папки.</span><span class="sxs-lookup"><span data-stu-id="d3460-139">Users of PowerShell 3.0 and later versions of PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="d3460-140">`Update-Help` Командлеты `Save-Help` и скрывают сведения об управлении от пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3460-140">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="d3460-141">Пользователи запускают `Update-Help` командлет, а затем используют `Get-Help` командлет для чтения самых новых файлов справки для модуля в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3460-141">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the PowerShell command prompt.</span></span>
<span data-ttu-id="d3460-142">Пользователям не нужно перезапускать Windows или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3460-142">Users do not need to restart Windows or PowerShell.</span></span>

<span data-ttu-id="d3460-143">Пользователи, находящиеся за брандмауэрами и без доступа к Интернету, могут также использовать обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="d3460-143">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span>
<span data-ttu-id="d3460-144">Администраторы с доступом к Интернету используют `Save-Help` командлет для загрузки и установки новых файлов справки в общую папку.</span><span class="sxs-lookup"><span data-stu-id="d3460-144">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="d3460-145">Затем пользователи используют параметр **path** `Update-Help` командлета, чтобы получить самые новые файлы справки из общей папки.</span><span class="sxs-lookup"><span data-stu-id="d3460-145">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="d3460-146">Авторы модулей могут включать файлы справки в модуль и использовать обновляемую справку для обновления файлов справки или опускать файлы справки из модуля и использовать обновляемую справку как для установки, так и для обновления.</span><span class="sxs-lookup"><span data-stu-id="d3460-146">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="d3460-147">Дополнительные сведения об обновляемой справке см. в разделе [Поддержка обновляемой справки](./supporting-updatable-help.md).</span><span class="sxs-lookup"><span data-stu-id="d3460-147">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="d3460-148">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="d3460-148">Supporting Online Help</span></span>

<span data-ttu-id="d3460-149">Пользователи, которые не могут устанавливать обновленные файлы справки на свои компьютеры, часто зависят от интерактивной версии разделов справки по модулям.</span><span class="sxs-lookup"><span data-stu-id="d3460-149">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="d3460-150">Параметр **Online** `Get-Help` командлета открывает Интернет-версию командлета или расширенного раздела справки по функциям для пользователя в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3460-150">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="d3460-151">`Get-Help` Командлет использует значение свойства **HelpUri** командлета или функции для поиска интерактивной версии раздела справки.</span><span class="sxs-lookup"><span data-stu-id="d3460-151">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="d3460-152">Начиная с версии PowerShell 3,0 можно помочь пользователям найти онлайн-версию командлетов и разделов справки по функциям, определив атрибут HelpUri в классе командлета или свойство **HelpUri** атрибута **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="d3460-152">Beginning in PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="d3460-153">Значением атрибута является значение свойства **HelpUri** командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="d3460-153">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="d3460-154">Дополнительные сведения см. в разделе [поддержка справки в Интернете](./supporting-online-help.md).</span><span class="sxs-lookup"><span data-stu-id="d3460-154">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3460-155">См. также</span><span class="sxs-lookup"><span data-stu-id="d3460-155">See Also</span></span>

[<span data-ttu-id="d3460-156">Написание модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3460-156">Writing a PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="d3460-157">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="d3460-157">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="d3460-158">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="d3460-158">Supporting Online Help</span></span>](./supporting-online-help.md)
