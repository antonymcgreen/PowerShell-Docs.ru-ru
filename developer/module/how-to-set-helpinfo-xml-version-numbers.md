---
title: Как задать номера версий HelpInfo XML | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: b98e6879bbfe0e3ec1a9ab37496dde44caf523a4
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054141"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="b4abc-102">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b4abc-102">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="b4abc-103">В этом разделе объясняется, как задать и повысить номера версии в файле обновляемые сведения, Справка, известную как «файл HelpInfo XML».</span><span class="sxs-lookup"><span data-stu-id="b4abc-103">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="b4abc-104">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b4abc-104">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="b4abc-105">Номера версий в XML-файл HelpInfo критически важны для работы обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="b4abc-105">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span>
<span data-ttu-id="b4abc-106">[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлеты загрузить новые файлы справки, только в том случае, если номер версии для языка и региональных параметров пользовательского интерфейса в удаленном файле HelpInfo XML больше, чем номер версии для этого языка и региональных параметров пользовательского интерфейса в локальный HelpInfo XML или нет локального файла HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="b4abc-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="b4abc-107">В файле HelpInfo XML используется номер версии 4 частей, который определен в **System.Version** класс Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b4abc-107">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="b4abc-108">Формат `N1.N2.N3.N4`.</span><span class="sxs-lookup"><span data-stu-id="b4abc-108">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="b4abc-109">Авторы модулей могут использовать любую версию нумерации, который разрешен в **System.Version** класса.</span><span class="sxs-lookup"><span data-stu-id="b4abc-109">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="b4abc-110">Обновляемая Справка требует только то, что номер версии увеличивать языка и региональных параметров пользовательского интерфейса при отправке новой версии CAB-файл для этой культуры пользовательского интерфейса в расположение, которое определяется **HelpContentURI** в файле HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="b4abc-110">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="b4abc-111">Приведенный ниже показаны элементы XML-файл HelpInfo для культуры немецкий (de-DE) пользовательского интерфейса при использовании версии 2.15.0.10.</span><span class="sxs-lookup"><span data-stu-id="b4abc-111">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="b4abc-112">Номер версии для культуры пользовательского интерфейса отражает версию CAB-файл для этой культуры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4abc-112">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="b4abc-113">Номер версии относится ко всему файлу CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="b4abc-113">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="b4abc-114">Невозможно задать разные номера версий для различные файлы в CAB-файл.</span><span class="sxs-lookup"><span data-stu-id="b4abc-114">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="b4abc-115">Номер версии для каждого языка пользовательского интерфейса вычисляется независимо друг от друга и не должны быть связаны с номера версий для других языков пользовательского интерфейса, которые поддерживает модуль.</span><span class="sxs-lookup"><span data-stu-id="b4abc-115">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>