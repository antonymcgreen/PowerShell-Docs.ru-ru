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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367013"
---
# <a name="naming-help-files"></a><span data-ttu-id="21f4b-102">Указание имен для файлов справки</span><span class="sxs-lookup"><span data-stu-id="21f4b-102">Naming Help Files</span></span>

<span data-ttu-id="21f4b-103">В этом разделе объясняется, как присвоить имя файлу справки на основе XML, чтобы командлет [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) мог его найти.</span><span class="sxs-lookup"><span data-stu-id="21f4b-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="21f4b-104">Требования к имени различаются для каждого типа команды.</span><span class="sxs-lookup"><span data-stu-id="21f4b-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="21f4b-105">Файлы справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="21f4b-105">Cmdlet Help Files</span></span>

<span data-ttu-id="21f4b-106">Файл справки для C# командлета должен называться для сборки, в которой определен командлет.</span><span class="sxs-lookup"><span data-stu-id="21f4b-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="21f4b-107">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="21f4b-107">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="21f4b-108">Формат имени сборки является обязательным, даже если сборка является вложенным модулем.</span><span class="sxs-lookup"><span data-stu-id="21f4b-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="21f4b-109">Например, [Get-WinEvent; PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) Командлет определен в сборке Microsoft. PowerShell. Diagnostics. dll.</span><span class="sxs-lookup"><span data-stu-id="21f4b-109">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="21f4b-110">Командлет `Get-Help` ищет раздел справки для командлета `Get-WinEvent` только в файле Microsoft. PowerShell. Diagnostics. длл-Хелп. XML в каталоге Module.</span><span class="sxs-lookup"><span data-stu-id="21f4b-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="21f4b-111">Файлы справки поставщика</span><span class="sxs-lookup"><span data-stu-id="21f4b-111">Provider Help files</span></span>

<span data-ttu-id="21f4b-112">Файл справки для поставщика Windows PowerShell должен называться для сборки, в которой определен поставщик.</span><span class="sxs-lookup"><span data-stu-id="21f4b-112">The help file for a Windows PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="21f4b-113">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="21f4b-113">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="21f4b-114">Формат имени сборки является обязательным, даже если сборка является вложенным модулем.</span><span class="sxs-lookup"><span data-stu-id="21f4b-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="21f4b-115">Например, поставщик сертификата определяется в сборке Microsoft. PowerShell. Security. dll.</span><span class="sxs-lookup"><span data-stu-id="21f4b-115">For example, the Certificate provider is defined in the Microsoft.PowerShell.Security.dll assembly.</span></span> <span data-ttu-id="21f4b-116">Командлет `Get-Help` ищет раздел справки для поставщика сертификатов только в файле Microsoft. PowerShell. Security. длл-Хелп. XML в каталоге Module.</span><span class="sxs-lookup"><span data-stu-id="21f4b-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the Microsoft.PowerShell.Security.dll-help.xml file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="21f4b-117">Файлы справки по функциям</span><span class="sxs-lookup"><span data-stu-id="21f4b-117">Function Help Files</span></span>

<span data-ttu-id="21f4b-118">Функции могут быть документированы с помощью [справки на основе комментариев](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) или документированы в файле справки XML.</span><span class="sxs-lookup"><span data-stu-id="21f4b-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="21f4b-119">Если функция задокументирована в XML-файле, функция должна иметь ключевое слово комментария `.ExternalHelp`, связывающее функцию с XML-файлом.</span><span class="sxs-lookup"><span data-stu-id="21f4b-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="21f4b-120">В противном случае командлету `Get-Help` не удастся найти файл справки.</span><span class="sxs-lookup"><span data-stu-id="21f4b-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="21f4b-121">Нет технических требований к имени файла справки функции.</span><span class="sxs-lookup"><span data-stu-id="21f4b-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="21f4b-122">Однако рекомендуется присвоить файлу справки имя модуля скрипта, в котором определена функция.</span><span class="sxs-lookup"><span data-stu-id="21f4b-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="21f4b-123">Например, в файле MyModule. PSM1 определена следующая функция.</span><span class="sxs-lookup"><span data-stu-id="21f4b-123">For example, the following function is defined in the MyModule.psm1 file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="21f4b-124">Файлы справки по командам CIM</span><span class="sxs-lookup"><span data-stu-id="21f4b-124">CIM Command Help Files</span></span>

<span data-ttu-id="21f4b-125">Файл справки для команды CIM должен называться для файла CDXML, в котором определена команда CIM.</span><span class="sxs-lookup"><span data-stu-id="21f4b-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="21f4b-126">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="21f4b-126">Use the following file name format:</span></span>

```
<FileName>.cdxml-help.xml
```

<span data-ttu-id="21f4b-127">Команды CIM определяются в файлах CDXML, которые могут быть включены в модули в качестве вложенных модулей.</span><span class="sxs-lookup"><span data-stu-id="21f4b-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="21f4b-128">При импорте команды CIM в сеанс в качестве функции Windows PowerShell добавляет к определению функции ключевое слово комментария `.ExternalHelp`, которое связывает функцию с файлом справки XML с именем для файла CDXML, в котором определена команда CIM.</span><span class="sxs-lookup"><span data-stu-id="21f4b-128">When the CIM command is imported into the session as a function, Windows PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="21f4b-129">Создать скрипт для файлов справки по рабочим процессам</span><span class="sxs-lookup"><span data-stu-id="21f4b-129">Script Workflow Help Files</span></span>

<span data-ttu-id="21f4b-130">Рабочие процессы сценариев, которые включены в модули, можно документировать в файлах справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="21f4b-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="21f4b-131">Нет технических требований к имени файла справки.</span><span class="sxs-lookup"><span data-stu-id="21f4b-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="21f4b-132">Однако рекомендуется присвоить файлу справки имя модуля скрипта, в котором определен рабочий процесс скрипта.</span><span class="sxs-lookup"><span data-stu-id="21f4b-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="21f4b-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="21f4b-133">For example:</span></span>

```
<ScriptModule>.psm1-help.xml
```

<span data-ttu-id="21f4b-134">В отличие от других команд, выполняемых в скрипте, рабочие процессы скриптов не занимают ключевое слово комментария `.ExternalHelp`, чтобы связать их с файлом справки.</span><span class="sxs-lookup"><span data-stu-id="21f4b-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="21f4b-135">Вместо этого Windows PowerShell выполняет поиск файлов справки на основе языка и региональных параметров пользовательского интерфейса в каталоге модуля, а также ищет справку по рабочему процессу сценария во всех файлах.</span><span class="sxs-lookup"><span data-stu-id="21f4b-135">Instead, Windows PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="21f4b-136">ключевое слово комментария `.ExternalHelp` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="21f4b-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="21f4b-137">Поскольку ключевое слово комментария `.ExternalHelp` игнорируется, командлет `Get-Help` может найти справку по сценарию для рабочих процессов, только если они включены в модули.</span><span class="sxs-lookup"><span data-stu-id="21f4b-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>