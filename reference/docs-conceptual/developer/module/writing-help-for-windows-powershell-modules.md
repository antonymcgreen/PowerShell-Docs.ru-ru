---
title: Написание справки для модулей Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360563"
---
# <a name="writing-help-for-windows-powershell-modules"></a><span data-ttu-id="3fadd-102">Написание справки для модулей Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fadd-102">Writing Help for Windows PowerShell Modules</span></span>

<span data-ttu-id="3fadd-103">Модули Windows PowerShell могут включать разделы справки о модуле и о членах модуля, таких как командлеты, поставщики, функции и скрипты.</span><span class="sxs-lookup"><span data-stu-id="3fadd-103">Windows PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="3fadd-104">Командлет `Get-Help` отображает разделы справки по модулям в том же формате, в котором отображается справка для других элементов Windows PowerShell, а для получения разделов справки пользователи используют стандартные команды `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="3fadd-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other Windows PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="3fadd-105">В этом документе описывается формат и правильное размещение разделов справки по модулям, а также приводятся рекомендации по использованию содержимого справки модуля.</span><span class="sxs-lookup"><span data-stu-id="3fadd-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="3fadd-106">Типы справки по модулям</span><span class="sxs-lookup"><span data-stu-id="3fadd-106">Types of Module Help</span></span>

<span data-ttu-id="3fadd-107">Модуль может включать следующие типы справки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="3fadd-108">**Справка по командлетам**.</span><span class="sxs-lookup"><span data-stu-id="3fadd-108">**Cmdlet Help**.</span></span> <span data-ttu-id="3fadd-109">Разделы справки, описывающие командлеты в модуле, — это XML-файлы, использующие схему справки по командам.</span><span class="sxs-lookup"><span data-stu-id="3fadd-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="3fadd-110">**Справка поставщика**.</span><span class="sxs-lookup"><span data-stu-id="3fadd-110">**Provider Help**.</span></span> <span data-ttu-id="3fadd-111">Разделы справки, в которых описываются поставщики в модуле, — это XML-файлы, использующие схему справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="3fadd-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="3fadd-112">**Справка по функциям**.</span><span class="sxs-lookup"><span data-stu-id="3fadd-112">**Function Help**.</span></span> <span data-ttu-id="3fadd-113">Разделы справки, описывающие функции в модуле, могут быть XML-файлами, которые используют схему справки команды или разделы справки на основе комментариев в функции, а также скрипт или модуль скрипта.</span><span class="sxs-lookup"><span data-stu-id="3fadd-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="3fadd-114">**Справка по скрипту**.</span><span class="sxs-lookup"><span data-stu-id="3fadd-114">**Script Help**.</span></span> <span data-ttu-id="3fadd-115">Разделы справки, описывающие скрипты в модуле, могут быть XML-файлами, которые используют схему справки команды или разделы справки на основе комментариев в модуле script или script.</span><span class="sxs-lookup"><span data-stu-id="3fadd-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="3fadd-116">**Концептуальная Справка ("о программе")** .</span><span class="sxs-lookup"><span data-stu-id="3fadd-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="3fadd-117">Концептуальный раздел справки ("About") можно использовать для описания модуля и его элементов, а также для объяснения того, как эти элементы можно использовать вместе для выполнения задач.</span><span class="sxs-lookup"><span data-stu-id="3fadd-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span> <span data-ttu-id="3fadd-118">Основные разделы справки — это текстовые файлы с кодировкой Юникод (UTF-8).</span><span class="sxs-lookup"><span data-stu-id="3fadd-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="3fadd-119">Имя файла должно использовать формат `about_<name>.help.txt`, например about_MyModule. Help. txt.</span><span class="sxs-lookup"><span data-stu-id="3fadd-119">The file name must use the `about_<name>.help.txt` format, such as about_MyModule.help.txt.</span></span> <span data-ttu-id="3fadd-120">По умолчанию Windows PowerShell включает более 100 этих концептуальных разделов справки и форматирует их, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3fadd-120">By default, Windows PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

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
      Text-only references for further reading. Hyperlinks cannot work in the Windows PowerShell console.

  ```

## <a name="placement-of-module-help"></a><span data-ttu-id="3fadd-121">Размещение справки по модулю</span><span class="sxs-lookup"><span data-stu-id="3fadd-121">Placement of Module Help</span></span>

<span data-ttu-id="3fadd-122">Командлет `Get-Help` ищет файлы разделов справки по модулям в подкаталогах, зависящих от языка, в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="3fadd-122">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="3fadd-123">Например, на следующей схеме структуры каталогов показано расположение разделов справки для модуля Самплемодуле.</span><span class="sxs-lookup"><span data-stu-id="3fadd-123">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="3fadd-124">В этом примере заполнитель *\<ModulePath >* представляет один из путей в переменной среды `PSModulePath`, например $Home \документс\модулес, $pshome \модулес или пользовательский путь, указываемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="3fadd-124">In the example, the *\<ModulePath>* placeholder represents one of the paths in the `PSModulePath` environment variable, such as $home\Documents\Modules, $pshome\Modules, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="3fadd-125">Получение справки по модулю</span><span class="sxs-lookup"><span data-stu-id="3fadd-125">Getting Module Help</span></span>

<span data-ttu-id="3fadd-126">Когда пользователь импортирует модуль в сеанс, разделы справки для этого модуля импортируются в сеанс вместе с модулем.</span><span class="sxs-lookup"><span data-stu-id="3fadd-126">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="3fadd-127">Файлы разделов справки можно вывести в значении ключа FileList в манифесте модуля, но на разделы справки не влияет командлет `Export-ModuleMember`.</span><span class="sxs-lookup"><span data-stu-id="3fadd-127">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="3fadd-128">Разделы справки по модулям можно предоставить на разных языках.</span><span class="sxs-lookup"><span data-stu-id="3fadd-128">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="3fadd-129">Командлет `Get-Help` автоматически отображает разделы справки по модулю на языке, указанном для текущего пользователя в разделе региональные и языковые параметры панели управления.</span><span class="sxs-lookup"><span data-stu-id="3fadd-129">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="3fadd-130">В Windows Vista и более поздних версиях Windows `Get-Help` ищет разделы справки в подкаталогах, относящихся к конкретному языку, в соответствии с стандартами переключения языка, установленными для Windows.</span><span class="sxs-lookup"><span data-stu-id="3fadd-130">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="3fadd-131">Начиная с Windows PowerShell 3,0, выполнение команды `Get-Help` для командлета или функции запускает автоматический импорт модуля.</span><span class="sxs-lookup"><span data-stu-id="3fadd-131">Beginning in Windows PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="3fadd-132">Командлет `Get-Help` сразу же отображает содержимое разделов справки в модуле.</span><span class="sxs-lookup"><span data-stu-id="3fadd-132">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="3fadd-133">Если модуль не содержит разделов справки и разделов справки для команд в модуле на компьютере пользователя, `Get-Help` отображает автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="3fadd-133">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="3fadd-134">Автоматически созданная Справка включает синтаксис команды, параметры, типы входных и выходных данных, но не содержит описания.</span><span class="sxs-lookup"><span data-stu-id="3fadd-134">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="3fadd-135">Автоматически созданная Справка содержит текст, указывающий пользователю на попытку использовать командлет `Update-Help` для загрузки справки по команде из Интернета или общей папки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-135">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="3fadd-136">Также рекомендуется использовать параметр **Online** командлета `Get-Help` для получения интерактивной версии раздела справки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-136">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="3fadd-137">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="3fadd-137">Supporting Updatable Help</span></span>

<span data-ttu-id="3fadd-138">Пользователи Windows PowerShell 3,0 и более поздних версий Windows PowerShell могут загружать и устанавливать обновленные файлы справки для модуля из Интернета или из локальной общей папки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-138">Users of Windows PowerShell 3.0 and later versions of Windows PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="3fadd-139">Командлеты `Update-Help` и `Save-Help` скрывают сведения об управлении от пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fadd-139">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="3fadd-140">Пользователи запускают командлет `Update-Help`, а затем используют командлет `Get-Help` для чтения самых новых файлов справки для модуля в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fadd-140">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the Windows PowerShell command prompt.</span></span> <span data-ttu-id="3fadd-141">Пользователям не нужно перезапускать Windows или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fadd-141">Users do not need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="3fadd-142">Пользователи, находящиеся за брандмауэрами и без доступа к Интернету, могут также использовать обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="3fadd-142">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span> <span data-ttu-id="3fadd-143">Администраторы с доступом к Интернету используют командлет `Save-Help` для загрузки и установки новых файлов справки в общую папку.</span><span class="sxs-lookup"><span data-stu-id="3fadd-143">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="3fadd-144">Затем пользователи используют параметр **path** командлета `Update-Help` для получения самых новых файлов справки из общей папки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-144">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="3fadd-145">Авторы модулей могут включать файлы справки в модуль и использовать обновляемую справку для обновления файлов справки или опускать файлы справки из модуля и использовать обновляемую справку как для установки, так и для обновления.</span><span class="sxs-lookup"><span data-stu-id="3fadd-145">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="3fadd-146">Дополнительные сведения об обновляемой справке см. в разделе [Поддержка обновляемой справки](./supporting-updatable-help.md).</span><span class="sxs-lookup"><span data-stu-id="3fadd-146">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="3fadd-147">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="3fadd-147">Supporting Online Help</span></span>

<span data-ttu-id="3fadd-148">Пользователи, которые не могут устанавливать обновленные файлы справки на свои компьютеры, часто зависят от интерактивной версии разделов справки по модулям.</span><span class="sxs-lookup"><span data-stu-id="3fadd-148">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="3fadd-149">Параметр **Online** командлета `Get-Help` открывает Интернет-версию командлета или расширенного раздела справки по функциям для пользователя в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3fadd-149">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="3fadd-150">Командлет `Get-Help` использует значение свойства **HelpUri** командлета или функции для поиска интерактивной версии раздела справки.</span><span class="sxs-lookup"><span data-stu-id="3fadd-150">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="3fadd-151">Начиная с Windows PowerShell 3,0, вы можете помочь пользователям найти онлайн-версию командлетов и разделов справки по функциям, определив атрибут HelpUri в классе командлета или свойство **HelpUri** атрибута **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="3fadd-151">Beginning in Windows PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="3fadd-152">Значением атрибута является значение свойства **HelpUri** командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="3fadd-152">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="3fadd-153">Дополнительные сведения см. в разделе [поддержка справки в Интернете](./supporting-online-help.md).</span><span class="sxs-lookup"><span data-stu-id="3fadd-153">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fadd-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="3fadd-154">See Also</span></span>

[<span data-ttu-id="3fadd-155">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fadd-155">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="3fadd-156">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="3fadd-156">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="3fadd-157">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="3fadd-157">Supporting Online Help</span></span>](./supporting-online-help.md)