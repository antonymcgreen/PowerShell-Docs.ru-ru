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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854070"
---
# <a name="writing-help-for-windows-powershell-modules"></a><span data-ttu-id="dd409-102">Написание справки для модулей Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd409-102">Writing Help for Windows PowerShell Modules</span></span>

<span data-ttu-id="dd409-103">Модули Windows PowerShell может включать разделы справки о модуле, а также о элементы модуля, такие как командлеты, поставщики, функции и сценарии.</span><span class="sxs-lookup"><span data-stu-id="dd409-103">Windows PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="dd409-104">`Get-Help` Командлет отображает раздел справки для модуля в том же формате, он отображает справку для других элементов Windows PowerShell, а пользователям использовать стандарт `Get-Help` команды, чтобы получить разделы справки.</span><span class="sxs-lookup"><span data-stu-id="dd409-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other Windows PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="dd409-105">В этом документе объясняется, формат и правильное размещение разделы справки для модуля, и предлагает рекомендации для содержимого справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="dd409-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="dd409-106">Типы модуля</span><span class="sxs-lookup"><span data-stu-id="dd409-106">Types of Module Help</span></span>

<span data-ttu-id="dd409-107">Модуль может включать следующие типы справки.</span><span class="sxs-lookup"><span data-stu-id="dd409-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="dd409-108">**Справку по командлетам**.</span><span class="sxs-lookup"><span data-stu-id="dd409-108">**Cmdlet Help**.</span></span> <span data-ttu-id="dd409-109">Разделы справки с описанием командлетов в модуле, что XML-файлов, используйте команду помогут схемы</span><span class="sxs-lookup"><span data-stu-id="dd409-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="dd409-110">**Справку по поставщикам**.</span><span class="sxs-lookup"><span data-stu-id="dd409-110">**Provider Help**.</span></span> <span data-ttu-id="dd409-111">Разделы справки, которые описывают поставщики в модуле — это XML-файлов, использующих поставщик справки схемы.</span><span class="sxs-lookup"><span data-stu-id="dd409-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="dd409-112">**Функциям**.</span><span class="sxs-lookup"><span data-stu-id="dd409-112">**Function Help**.</span></span> <span data-ttu-id="dd409-113">Разделы справки, которые описывают функции в модуле может быть, что XML-файлов, используйте команду помогут схемы или основанной на комментариях разделы справки, функции или скрипта или модуля сценария</span><span class="sxs-lookup"><span data-stu-id="dd409-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="dd409-114">**Сценариям**.</span><span class="sxs-lookup"><span data-stu-id="dd409-114">**Script Help**.</span></span> <span data-ttu-id="dd409-115">Разделы справки, которые описывают скрипты в модуле может быть XML-файлов, используйте команду справки схемы или разделы справки на основе комментариев в скрипте или модуль сценария.</span><span class="sxs-lookup"><span data-stu-id="dd409-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="dd409-116">**(«О программе») справки**.</span><span class="sxs-lookup"><span data-stu-id="dd409-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="dd409-117">Можно использовать общие («about») раздела справки для описания модуля и его членах и объяснить, как члены могут использоваться совместно для выполнения задач.</span><span class="sxs-lookup"><span data-stu-id="dd409-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span> <span data-ttu-id="dd409-118">Разделы справки — это текстовые файлы в кодировке Юникод (UTF-8).</span><span class="sxs-lookup"><span data-stu-id="dd409-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="dd409-119">Имя файла необходимо использовать `about_<name>.help.txt` формат, например about_MyModule.help.txt.</span><span class="sxs-lookup"><span data-stu-id="dd409-119">The file name must use the `about_<name>.help.txt` format, such as about_MyModule.help.txt.</span></span> <span data-ttu-id="dd409-120">По умолчанию Windows PowerShell содержит более чем 100 этих концептуальных разделов справки, и они форматируются как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dd409-120">By default, Windows PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

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

## <a name="placement-of-module-help"></a><span data-ttu-id="dd409-121">Размещение Справка по модулям</span><span class="sxs-lookup"><span data-stu-id="dd409-121">Placement of Module Help</span></span>

<span data-ttu-id="dd409-122">`Get-Help` Командлет ищет файлы разделов справки модуля в языку каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="dd409-122">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="dd409-123">Например на следующей схеме структура каталогов показывает расположение разделов справки по модулю SampleModule.</span><span class="sxs-lookup"><span data-stu-id="dd409-123">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="dd409-124">В примере  *\<ModulePath >* заполнитель представляет один из путей в `PSModulePath` переменной среды, например $home\Documents\Modules, $pshome\Modules или пользовательского пути, задаваемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="dd409-124">In the example, the *\<ModulePath>* placeholder represents one of the paths in the `PSModulePath` environment variable, such as $home\Documents\Modules, $pshome\Modules, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="dd409-125">Получение справки для модуля</span><span class="sxs-lookup"><span data-stu-id="dd409-125">Getting Module Help</span></span>

<span data-ttu-id="dd409-126">Когда пользователь импортирует модуль в сеанс, разделы справки для этого модуля, импортируются в сеанс вместе с модулем.</span><span class="sxs-lookup"><span data-stu-id="dd409-126">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="dd409-127">Вы можете получить список файлов справки в значении ключа FileList в манифесте модуля, но разделы справки, не подвержены `Export-ModuleMember` командлета.</span><span class="sxs-lookup"><span data-stu-id="dd409-127">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="dd409-128">Вы можете предоставить модуль разделы справки на разных языках.</span><span class="sxs-lookup"><span data-stu-id="dd409-128">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="dd409-129">`Get-Help` Командлет автоматически отображает разделы справки для модуля на языке, который указан для текущего пользователя в «язык и региональные стандарты» панели управления.</span><span class="sxs-lookup"><span data-stu-id="dd409-129">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="dd409-130">В Windows Vista и более поздних версиях Windows `Get-Help` поиск разделов справки в языку каталога модуля в соответствии со стандартами резервный язык, установленным для Windows.</span><span class="sxs-lookup"><span data-stu-id="dd409-130">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="dd409-131">Начиная с Windows PowerShell 3.0, под управлением `Get-Help` запускает команду, командлет или функцию, автоматический импорт модуля.</span><span class="sxs-lookup"><span data-stu-id="dd409-131">Beginning in Windows PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="dd409-132">`Get-Help` Командлет сразу отображает содержимое разделов справки в модуле.</span><span class="sxs-lookup"><span data-stu-id="dd409-132">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="dd409-133">Если модуль содержит разделы справки, а не разделы справки по командам модуля на компьютере пользователя, `Get-Help` выводит автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="dd409-133">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="dd409-134">Автоматически собранную справку входит синтаксис команды, параметры и типы входных и выходных данных, но не включает все описания.</span><span class="sxs-lookup"><span data-stu-id="dd409-134">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="dd409-135">Текст, который предлагает пользователю попробуйте использовать содержит автоматически созданную справку `Update-Help` командлет, чтобы загрузить справку по командам из Интернета или общей папки.</span><span class="sxs-lookup"><span data-stu-id="dd409-135">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="dd409-136">Также рекомендуется с помощью **Online** параметр `Get-Help` для получения Интернет-версию раздела справки.</span><span class="sxs-lookup"><span data-stu-id="dd409-136">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="dd409-137">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="dd409-137">Supporting Updatable Help</span></span>

<span data-ttu-id="dd409-138">Пользователи Windows PowerShell 3.0 и более поздних версиях Windows PowerShell можно загрузить и установить обновленные файлы справки для модуля из Интернета или из локальной общей папки.</span><span class="sxs-lookup"><span data-stu-id="dd409-138">Users of Windows PowerShell 3.0 and later versions of Windows PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="dd409-139">`Update-Help` И `Save-Help` командлеты скрыть сведения управления от пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd409-139">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="dd409-140">Пользователей, работающих с `Update-Help` командлет, а затем использовать `Get-Help` командлет, чтобы читать последние файлы справки для модуля в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd409-140">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the Windows PowerShell command prompt.</span></span> <span data-ttu-id="dd409-141">Пользователям не обязательно должны перезапускать Windows или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd409-141">Users do not need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="dd409-142">Пользователи за брандмауэрами и без доступа к Интернету можно использовать обновляемую справку, а также.</span><span class="sxs-lookup"><span data-stu-id="dd409-142">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span> <span data-ttu-id="dd409-143">Администраторы с Интернетом, доступ к используйте `Save-Help` командлет, чтобы загрузить и установить новейшие файлы справки для общей папки.</span><span class="sxs-lookup"><span data-stu-id="dd409-143">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="dd409-144">Затем с помощью пользователей **путь** параметр `Update-Help` командлет, чтобы получить последние файлы справки из общей папки.</span><span class="sxs-lookup"><span data-stu-id="dd409-144">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="dd409-145">Авторы модулей могут входят файлы справки в модуле и использовать обновляемую справку, обновления файлов справки, или пропустить файлы справки из модуля и использовать обновляемую справку для установки и для их обновления.</span><span class="sxs-lookup"><span data-stu-id="dd409-145">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="dd409-146">Дополнительные сведения об обновляемой справке см. в разделе [поддержка обновляемой справки](./supporting-updatable-help.md).</span><span class="sxs-lookup"><span data-stu-id="dd409-146">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="dd409-147">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="dd409-147">Supporting Online Help</span></span>

<span data-ttu-id="dd409-148">Пользователей, которые нельзя или не устанавливайте обновления помогают на своих компьютерах файлы часто полагаются на Интернет-версию разделов справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="dd409-148">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="dd409-149">**Online** параметр `Get-Help` командлет открывает Интернет-версию командлет или дополнительную функцию раздел справки для пользователя в своих веб-браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd409-149">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="dd409-150">`Get-Help` Командлет использует значение **HelpUri** свойства командлета или функции, чтобы найти Интернет-версию раздела справки.</span><span class="sxs-lookup"><span data-stu-id="dd409-150">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="dd409-151">Начиная с Windows PowerShell 3.0, вы можете помочь пользователям найти Интернет-версию разделов справки для командлетов и функций, определив атрибута HelpUri в классе командлета или **HelpUri** свойство **CmdletBinding** атрибута.</span><span class="sxs-lookup"><span data-stu-id="dd409-151">Beginning in Windows PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="dd409-152">Значение атрибута является значение **HelpUri** свойства командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="dd409-152">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="dd409-153">Дополнительные сведения см. в разделе [поддержка справки в Интернете](./supporting-online-help.md).</span><span class="sxs-lookup"><span data-stu-id="dd409-153">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd409-154">См. также</span><span class="sxs-lookup"><span data-stu-id="dd409-154">See Also</span></span>

[<span data-ttu-id="dd409-155">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd409-155">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="dd409-156">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="dd409-156">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="dd409-157">Поддержке справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="dd409-157">Supporting Online Help</span></span>](./supporting-online-help.md)