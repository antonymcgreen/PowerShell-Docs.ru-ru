---
ms.date: 09/12/2016
ms.topic: reference
title: Как задать номера версий XML-файла HelpInfo
description: Как задать номера версий XML-файла HelpInfo
ms.openlocfilehash: 9ef1940ca05d8aa9b04770013287490b71c8065a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658830"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="fc36b-103">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fc36b-103">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="fc36b-104">В этом разделе объясняется, как задать и увеличить номера версий в файле обновляемой справочной информации, который обычно называется XML-файлом HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="fc36b-104">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="fc36b-105">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fc36b-105">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="fc36b-106">Номера версий в XML-файле HelpInfo критически важны для работы обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="fc36b-106">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span> <span data-ttu-id="fc36b-107">Командлеты [Update — Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) загружают новые файлы справки только в том случае, если номер версии языка и региональных параметров пользовательского интерфейса в удаленном XML-файле HelpInfo больше номера версии для этого языка и региональных параметров пользовательского интерфейса в локальном HelpInfo XML или отсутствует локальный XML-файл HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="fc36b-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="fc36b-108">XML-файл HelpInfo использует номер версии из 4 частей, определенный в классе **System. Version** платформы Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc36b-108">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="fc36b-109">Формат — `N1.N2.N3.N4`.</span><span class="sxs-lookup"><span data-stu-id="fc36b-109">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="fc36b-110">Авторы модулей могут использовать любую схему нумерации версий, которая разрешена классом **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="fc36b-110">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="fc36b-111">Для обновляемой справки необходимо, чтобы номер версии языка и региональных параметров пользовательского интерфейса был увеличен, когда новая версия CAB-файла для этого языка и региональных параметров пользовательского интерфейса передается в расположение, указанное элементом **хелпконтентури** в файле XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="fc36b-111">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="fc36b-112">В следующем примере показаны элементы XML-файла HelpInfo для языка и региональных параметров (de-DE) пользовательского интерфейса, если версия 2.15.0.10.</span><span class="sxs-lookup"><span data-stu-id="fc36b-112">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml
<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="fc36b-113">Номер версии языка и региональных параметров пользовательского интерфейса отражает версию CAB-файла для этого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="fc36b-113">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="fc36b-114">Номер версии применяется ко всему CAB-файлу.</span><span class="sxs-lookup"><span data-stu-id="fc36b-114">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="fc36b-115">Нельзя задать разные номера версий для разных файлов в CAB-файле.</span><span class="sxs-lookup"><span data-stu-id="fc36b-115">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="fc36b-116">Номер версии для каждого языка и региональных параметров пользовательского интерфейса вычисляется независимо друг от друга и не должен быть связан с номерами версий других культур пользовательского интерфейса, поддерживаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="fc36b-116">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>
