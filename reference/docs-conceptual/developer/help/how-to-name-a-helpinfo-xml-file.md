---
ms.date: 09/12/2016
ms.topic: reference
title: Как назвать XML-файл HelpInfo
description: Как назвать XML-файл HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659044"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="dae6c-103">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="dae6c-103">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="dae6c-104">В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="dae6c-104">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="dae6c-105">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="dae6c-105">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="dae6c-106">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="dae6c-106">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="dae6c-107">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="dae6c-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="dae6c-108">`<ModuleName>` — Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="dae6c-108">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="dae6c-109">`<ModuleGUID>` — Значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="dae6c-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="dae6c-110">Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dae6c-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
