---
title: Как назвать CAB-файл обновляемой справки
ms.date: 09/12/2016
ms.openlocfilehash: 42486461d92f1f6fcff452a4539edf5be7a66f22
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893005"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="45117-102">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="45117-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="45117-103">В этом разделе описывается требуемый формат имени для обновляемых файлов CAB-файла справки ( `.CAB` ).</span><span class="sxs-lookup"><span data-stu-id="45117-103">This topic explains the required name format for the Updatable Help cabinet (`.CAB`) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="45117-104">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="45117-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="45117-105">Обновляемый файл CAB ( `.CAB` ) должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="45117-105">A Updatable cabinet (`.CAB`) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="45117-106">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="45117-106">The elements of the name are as follows.</span></span>

- <span data-ttu-id="45117-107">`<ModuleName>`— Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="45117-107">`<ModuleName>` -The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
- <span data-ttu-id="45117-108">`<ModuleGUID>`— Значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="45117-108">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>
- <span data-ttu-id="45117-109">`<UICulture>`— Язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле.</span><span class="sxs-lookup"><span data-stu-id="45117-109">`<UICulture>` - The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="45117-110">Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="45117-110">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="45117-111">Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45117-111">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
