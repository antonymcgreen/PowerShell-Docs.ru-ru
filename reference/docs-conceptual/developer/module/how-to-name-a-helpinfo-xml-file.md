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
ms.openlocfilehash: 462cd7bd486a5924bb2bc43e0ac8d1558e30e657
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367203"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="d0fe4-102">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="d0fe4-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="d0fe4-103">В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="d0fe4-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="d0fe4-104">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="d0fe4-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="d0fe4-105">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="d0fe4-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="d0fe4-106">Ниже приведены элементы имени.</span><span class="sxs-lookup"><span data-stu-id="d0fe4-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="d0fe4-107">ModuleName значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .</span><span class="sxs-lookup"><span data-stu-id="d0fe4-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="d0fe4-108">Модулегуид значение ключа **GUID** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="d0fe4-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="d0fe4-109">Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0fe4-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`