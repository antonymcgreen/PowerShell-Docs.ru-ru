---
title: Как назвать XML-файл HelpInfo
ms.date: 09/12/2016
ms.openlocfilehash: 9505a7f66852a569d25ac0c1be86e68f870a7930
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892937"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6873b-102">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6873b-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6873b-103">В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="6873b-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6873b-104">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6873b-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6873b-105">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="6873b-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="6873b-106">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="6873b-106">The elements of the name are as follows.</span></span>

- <span data-ttu-id="6873b-107">`<ModuleName>`— Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="6873b-107">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="6873b-108">`<ModuleGUID>`— Значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="6873b-108">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="6873b-109">Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6873b-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
