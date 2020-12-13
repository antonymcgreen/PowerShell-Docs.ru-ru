---
ms.date: 09/12/2016
ms.topic: reference
title: Как назвать CAB-файл обновляемой справки
description: Как назвать CAB-файл обновляемой справки
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658922"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="c193c-103">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="c193c-103">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="c193c-104">В этом разделе описывается требуемый формат имени для обновляемых файлов CAB-файла справки ( `.CAB` ).</span><span class="sxs-lookup"><span data-stu-id="c193c-104">This topic explains the required name format for the Updatable Help cabinet (`.CAB`) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="c193c-105">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="c193c-105">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="c193c-106">Обновляемый файл CAB ( `.CAB` ) должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="c193c-106">A Updatable cabinet (`.CAB`) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="c193c-107">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="c193c-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="c193c-108">`<ModuleName>` — Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="c193c-108">`<ModuleName>` -The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
- <span data-ttu-id="c193c-109">`<ModuleGUID>` — Значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="c193c-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>
- <span data-ttu-id="c193c-110">`<UICulture>` — Язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле.</span><span class="sxs-lookup"><span data-stu-id="c193c-110">`<UICulture>` - The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="c193c-111">Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="c193c-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="c193c-112">Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c193c-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
