---
title: Именование файлов справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: f65a90023df88fceafae1d1875ddf46b9088e2b8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082187"
---
# <a name="naming-help-files"></a><span data-ttu-id="9df21-102">Указание имен для файлов справки</span><span class="sxs-lookup"><span data-stu-id="9df21-102">Naming Help Files</span></span>

<span data-ttu-id="9df21-103">В этом разделе объясняется, как имя файла справки на основе XML, чтобы [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета можно найти его.</span><span class="sxs-lookup"><span data-stu-id="9df21-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="9df21-104">Требования к имени зависят от типа команды.</span><span class="sxs-lookup"><span data-stu-id="9df21-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="9df21-105">Файлы справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="9df21-105">Cmdlet Help Files</span></span>

<span data-ttu-id="9df21-106">Файл справки для C# командлет должен иметь имя для сборки, в котором определен этот командлет.</span><span class="sxs-lookup"><span data-stu-id="9df21-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="9df21-107">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="9df21-107">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="9df21-108">Формат имени сборки является обязательным, даже в том случае, если сборка является вложенного модуля.</span><span class="sxs-lookup"><span data-stu-id="9df21-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="9df21-109">Например [Get-WinEvent; PSITPro5_Diagnostic; ](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) командлет определен в сборке Microsoft.PowerShell.Diagnostics.dll.</span><span class="sxs-lookup"><span data-stu-id="9df21-109">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="9df21-110">`Get-Help` Командлет ищет раздел справки для `Get-WinEvent` командлет только в файле Microsoft.PowerShell.Diagnostics.dll help.xml в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="9df21-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="9df21-111">Файлы справки поставщика</span><span class="sxs-lookup"><span data-stu-id="9df21-111">Provider Help files</span></span>

<span data-ttu-id="9df21-112">Для сборки, в которой определен поставщик должен называться файл справки для поставщика Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9df21-112">The help file for a Windows PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="9df21-113">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="9df21-113">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="9df21-114">Формат имени сборки является обязательным, даже в том случае, если сборка является вложенного модуля.</span><span class="sxs-lookup"><span data-stu-id="9df21-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="9df21-115">Например поставщик Certificate определяется в сборке Microsoft.PowerShell.Security.dll.</span><span class="sxs-lookup"><span data-stu-id="9df21-115">For example, the Certificate provider is defined in the Microsoft.PowerShell.Security.dll assembly.</span></span> <span data-ttu-id="9df21-116">`Get-Help` Командлет ищет раздел справки по поставщику Certificate только в файле Microsoft.PowerShell.Security.dll help.xml в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="9df21-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the Microsoft.PowerShell.Security.dll-help.xml file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="9df21-117">Файлы справки для функции</span><span class="sxs-lookup"><span data-stu-id="9df21-117">Function Help Files</span></span>

<span data-ttu-id="9df21-118">Функции можно задокументировать с помощью [справки на основе комментариев](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) или в XML-файл справки.</span><span class="sxs-lookup"><span data-stu-id="9df21-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="9df21-119">Когда функция описана в XML-файл, функция должна иметь `.ExternalHelp` комментарий ключевое слово, которое связывает функцию с XML-файле.</span><span class="sxs-lookup"><span data-stu-id="9df21-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="9df21-120">В противном случае `Get-Help` командлету не удается найти файл справки.</span><span class="sxs-lookup"><span data-stu-id="9df21-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="9df21-121">Не существует технических требований к имени файла справки функции.</span><span class="sxs-lookup"><span data-stu-id="9df21-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="9df21-122">Тем не менее мы рекомендуем для именования файла справки для модуля сценария, в котором определена функция.</span><span class="sxs-lookup"><span data-stu-id="9df21-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="9df21-123">Например следующая функция определяется в файле MyModule.psm1.</span><span class="sxs-lookup"><span data-stu-id="9df21-123">For example, the following function is defined in the MyModule.psm1 file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="9df21-124">Файлы справки для команд CIM</span><span class="sxs-lookup"><span data-stu-id="9df21-124">CIM Command Help Files</span></span>

<span data-ttu-id="9df21-125">Файл справки для команд CIM должен иметь имя для файла CDXML, в котором определен команды CIM.</span><span class="sxs-lookup"><span data-stu-id="9df21-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="9df21-126">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="9df21-126">Use the following file name format:</span></span>

```
<FileName>.cdxml-help.xml
```

<span data-ttu-id="9df21-127">Команды CIM, определяются в CDXML-файлы, которые могут быть включены в модулях, как вложенные модули.</span><span class="sxs-lookup"><span data-stu-id="9df21-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="9df21-128">При импорте команды CIM в сеанс как функции Windows PowerShell добавляет `.ExternalHelp` комментарий, ключевое слово в определении функции, который связывает функцию с помощью XML файл, который совпадает с именем файла CDXML, в котором определен команды CIM.</span><span class="sxs-lookup"><span data-stu-id="9df21-128">When the CIM command is imported into the session as a function, Windows PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="9df21-129">Файлы справки для рабочего процесса сценария</span><span class="sxs-lookup"><span data-stu-id="9df21-129">Script Workflow Help Files</span></span>

<span data-ttu-id="9df21-130">Рабочие процессы сценариев, включенных в модулях документируется в файлы справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="9df21-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="9df21-131">Не существует технических требований к имени файла справки.</span><span class="sxs-lookup"><span data-stu-id="9df21-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="9df21-132">Тем не менее мы рекомендуем для именования файла справки для модуля сценария, в котором определен рабочем процессе сценария.</span><span class="sxs-lookup"><span data-stu-id="9df21-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="9df21-133">Например:</span><span class="sxs-lookup"><span data-stu-id="9df21-133">For example:</span></span>

```
<ScriptModule>.psm1-help.xml
```

<span data-ttu-id="9df21-134">В отличие от других скриптовые команды рабочих процессах сценариев не требуют `.ExternalHelp` комментарий ключевое слово, чтобы связать их с файлом справки.</span><span class="sxs-lookup"><span data-stu-id="9df21-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="9df21-135">Вместо этого Windows PowerShell выполняет подкаталоги каталога модуля файлы справки на основе XML для конкретного языка и региональных параметров пользовательского интерфейса и ищет справку для рабочего процесса сценария во всех файлах.</span><span class="sxs-lookup"><span data-stu-id="9df21-135">Instead, Windows PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="9df21-136">`.ExternalHelp` Ключевое слово комментария, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9df21-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="9df21-137">Так как `.ExternalHelp` комментарий ключевого слова пропускается, `Get-Help` командлета можно найти справки для рабочих процессов для сценариев, только в том случае, если они включены в модулях.</span><span class="sxs-lookup"><span data-stu-id="9df21-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>