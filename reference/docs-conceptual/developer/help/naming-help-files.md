---
ms.date: 09/12/2016
ms.topic: reference
title: Указание имен для файлов справки
description: Указание имен для файлов справки
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667595"
---
# <a name="naming-help-files"></a><span data-ttu-id="e61b1-103">Указание имен для файлов справки</span><span class="sxs-lookup"><span data-stu-id="e61b1-103">Naming Help Files</span></span>

<span data-ttu-id="e61b1-104">В этом разделе объясняется, как присвоить имя файлу справки на основе XML, чтобы командлет [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) мог его найти.</span><span class="sxs-lookup"><span data-stu-id="e61b1-104">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="e61b1-105">Требования к имени различаются для каждого типа команды.</span><span class="sxs-lookup"><span data-stu-id="e61b1-105">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="e61b1-106">Файлы справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="e61b1-106">Cmdlet Help Files</span></span>

<span data-ttu-id="e61b1-107">Файл справки для командлета C# должен называться для сборки, в которой определен командлет.</span><span class="sxs-lookup"><span data-stu-id="e61b1-107">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="e61b1-108">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="e61b1-108">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="e61b1-109">Формат имени сборки является обязательным, даже если сборка является вложенным модулем.</span><span class="sxs-lookup"><span data-stu-id="e61b1-109">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="e61b1-110">Например, командлет [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) определяется в сборке Microsoft.PowerShell.Diagnostics.dll.</span><span class="sxs-lookup"><span data-stu-id="e61b1-110">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="e61b1-111">`Get-Help`Командлет ищет раздел справки для `Get-WinEvent` командлета только в `Microsoft.PowerShell.Diagnostics.dll-help.xml` файле в каталоге Module.</span><span class="sxs-lookup"><span data-stu-id="e61b1-111">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="e61b1-112">Файлы справки поставщика</span><span class="sxs-lookup"><span data-stu-id="e61b1-112">Provider Help files</span></span>

<span data-ttu-id="e61b1-113">Файл справки для поставщика PowerShell должен называться для сборки, в которой определен поставщик.</span><span class="sxs-lookup"><span data-stu-id="e61b1-113">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="e61b1-114">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="e61b1-114">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="e61b1-115">Формат имени сборки является обязательным, даже если сборка является вложенным модулем.</span><span class="sxs-lookup"><span data-stu-id="e61b1-115">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="e61b1-116">Например, поставщик сертификата определяется в `Microsoft.PowerShell.Security.dll` сборке.</span><span class="sxs-lookup"><span data-stu-id="e61b1-116">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="e61b1-117">`Get-Help`Командлет ищет раздел справки для поставщика сертификатов только в `Microsoft.PowerShell.Security.dll-help.xml` файле в каталоге Module.</span><span class="sxs-lookup"><span data-stu-id="e61b1-117">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="e61b1-118">Файлы справки по функциям</span><span class="sxs-lookup"><span data-stu-id="e61b1-118">Function Help Files</span></span>

<span data-ttu-id="e61b1-119">Функции могут быть документированы с помощью [справки на основе комментариев](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) или документированы в файле справки XML.</span><span class="sxs-lookup"><span data-stu-id="e61b1-119">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="e61b1-120">Если функция задокументирована в XML-файле, функция должна иметь `.ExternalHelp` ключевое слово Comment, которое связывает функцию с XML-файлом.</span><span class="sxs-lookup"><span data-stu-id="e61b1-120">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="e61b1-121">В противном случае `Get-Help` командлет не сможет найти файл справки.</span><span class="sxs-lookup"><span data-stu-id="e61b1-121">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="e61b1-122">Нет технических требований к имени файла справки функции.</span><span class="sxs-lookup"><span data-stu-id="e61b1-122">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="e61b1-123">Однако рекомендуется присвоить файлу справки имя модуля скрипта, в котором определена функция.</span><span class="sxs-lookup"><span data-stu-id="e61b1-123">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="e61b1-124">Например, в файле определена следующая функция `MyModule.psm1` .</span><span class="sxs-lookup"><span data-stu-id="e61b1-124">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="e61b1-125">Файлы справки по командам CIM</span><span class="sxs-lookup"><span data-stu-id="e61b1-125">CIM Command Help Files</span></span>

<span data-ttu-id="e61b1-126">Файл справки для команды CIM должен называться для файла CDXML, в котором определена команда CIM.</span><span class="sxs-lookup"><span data-stu-id="e61b1-126">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="e61b1-127">Используйте следующий формат имени файла:</span><span class="sxs-lookup"><span data-stu-id="e61b1-127">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="e61b1-128">Команды CIM определяются в файлах CDXML, которые могут быть включены в модули в качестве вложенных модулей.</span><span class="sxs-lookup"><span data-stu-id="e61b1-128">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="e61b1-129">При импорте команды CIM в сеанс в качестве функции PowerShell добавляет `.ExternalHelp` к определению функции ключевое слово Comment, связывающее функцию с файлом справки XML с именем для CDXML-файла, в котором определена команда CIM.</span><span class="sxs-lookup"><span data-stu-id="e61b1-129">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="e61b1-130">Создать скрипт для файлов справки по рабочим процессам</span><span class="sxs-lookup"><span data-stu-id="e61b1-130">Script Workflow Help Files</span></span>

<span data-ttu-id="e61b1-131">Рабочие процессы сценариев, которые включены в модули, можно документировать в файлах справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="e61b1-131">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="e61b1-132">Нет технических требований к имени файла справки.</span><span class="sxs-lookup"><span data-stu-id="e61b1-132">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="e61b1-133">Однако рекомендуется присвоить файлу справки имя модуля скрипта, в котором определен рабочий процесс скрипта.</span><span class="sxs-lookup"><span data-stu-id="e61b1-133">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="e61b1-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="e61b1-134">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="e61b1-135">В отличие от других команд, выполняемых в скрипте, рабочие процессы скриптов не занимают `.ExternalHelp` ключевое слово Comment, чтобы связать их с файлом справки.</span><span class="sxs-lookup"><span data-stu-id="e61b1-135">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="e61b1-136">Вместо этого PowerShell выполняет поиск файлов справки на основе языка и региональных параметров пользовательского интерфейса в каталоге модуля, а также ищет справку по рабочему процессу сценария во всех файлах.</span><span class="sxs-lookup"><span data-stu-id="e61b1-136">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="e61b1-137">`.ExternalHelp` ключевое слово Comment игнорируется.</span><span class="sxs-lookup"><span data-stu-id="e61b1-137">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="e61b1-138">Поскольку `.ExternalHelp` ключевое слово Comment игнорируется, `Get-Help` командлет может найти справку по сценарию для рабочих процессов, только если они включены в модули.</span><span class="sxs-lookup"><span data-stu-id="e61b1-138">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
