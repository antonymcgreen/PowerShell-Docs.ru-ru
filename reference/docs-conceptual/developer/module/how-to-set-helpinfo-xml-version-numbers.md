---
title: Как задать номера версий XML для HelpInfo | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: 864372bfb0f43922f6066ff3db19956a7942db49
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560531"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="ec4ca-102">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="ec4ca-102">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="ec4ca-103">В этом разделе объясняется, как задать и увеличить номера версий в файле обновляемой справочной информации, который обычно называется XML-файлом HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-103">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="ec4ca-104">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="ec4ca-104">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="ec4ca-105">Номера версий в XML-файле HelpInfo критически важны для работы обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-105">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span>
<span data-ttu-id="ec4ca-106">Командлеты [Update — Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) загружают новые файлы справки только в том случае, если номер версии языка и региональных параметров пользовательского интерфейса в удаленном XML-файле HelpInfo больше номера версии для этого языка и региональных параметров пользовательского интерфейса в локальном HelpInfo XML или отсутствует локальный XML-файл HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="ec4ca-107">XML-файл HelpInfo использует номер версии из 4 частей, определенный в классе **System. Version** платформы Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-107">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="ec4ca-108">Формат — `N1.N2.N3.N4`.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-108">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="ec4ca-109">Авторы модулей могут использовать любую схему нумерации версий, которая разрешена классом **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="ec4ca-109">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="ec4ca-110">Для обновляемой справки необходимо, чтобы номер версии языка и региональных параметров пользовательского интерфейса был увеличен, когда новая версия CAB-файла для этого языка и региональных параметров пользовательского интерфейса передается в расположение, указанное элементом **хелпконтентури** в файле XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-110">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="ec4ca-111">В следующем примере показаны элементы XML-файла HelpInfo для языка и региональных параметров (de-DE) пользовательского интерфейса, если версия 2.15.0.10.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-111">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="ec4ca-112">Номер версии языка и региональных параметров пользовательского интерфейса отражает версию CAB-файла для этого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-112">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="ec4ca-113">Номер версии применяется ко всему CAB-файлу.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-113">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="ec4ca-114">Нельзя задать разные номера версий для разных файлов в CAB-файле.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-114">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="ec4ca-115">Номер версии для каждого языка и региональных параметров пользовательского интерфейса вычисляется независимо друг от друга и не должен быть связан с номерами версий других культур пользовательского интерфейса, поддерживаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="ec4ca-115">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>
