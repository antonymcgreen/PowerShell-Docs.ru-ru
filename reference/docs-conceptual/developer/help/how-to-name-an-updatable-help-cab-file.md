---
title: Именование обновляемого CAB-файла справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: a253f98d213f797a659affb1560907bb99a045d3
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811703"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="3b817-102">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="3b817-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="3b817-103">В этом разделе описывается требуемый формат имени для обновляемого CAB-файла справки (. CAB-файлы).</span><span class="sxs-lookup"><span data-stu-id="3b817-103">This topic explains the required name format for the Updatable Help cabinet (.CAB) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="3b817-104">Как назвать CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="3b817-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="3b817-105">Обновляемый CAB-файл (. CAB-файл) должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="3b817-105">A Updatable cabinet (.CAB) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="3b817-106">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="3b817-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="3b817-107">ModuleName значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="3b817-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="3b817-108">Модулегуид значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="3b817-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="3b817-109">UICulture язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле.</span><span class="sxs-lookup"><span data-stu-id="3b817-109">UICulture The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="3b817-110">Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="3b817-110">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="3b817-111">Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3b817-111">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
