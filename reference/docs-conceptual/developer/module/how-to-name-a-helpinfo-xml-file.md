---
title: Как присвоить имя XML-файлу HelpInfo | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e85b53-5aeb-4d6c-903c-af4ab62f11c1
caps.latest.revision: 7
ms.openlocfilehash: 45e8a5bb0066f38c82cd3be8ec881383befd9c85
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560582"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="fa041-102">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fa041-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="fa041-103">В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="fa041-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="fa041-104">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fa041-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="fa041-105">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="fa041-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="fa041-106">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="fa041-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="fa041-107">ModuleName значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="fa041-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="fa041-108">Модулегуид значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="fa041-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="fa041-109">Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fa041-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
