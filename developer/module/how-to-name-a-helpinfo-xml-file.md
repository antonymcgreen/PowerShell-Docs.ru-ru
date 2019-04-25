---
title: Принципы присвоения имен XML-файл HelpInfo | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e85b53-5aeb-4d6c-903c-af4ab62f11c1
caps.latest.revision: 7
ms.openlocfilehash: 462cd7bd486a5924bb2bc43e0ac8d1558e30e657
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082402"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="31321-102">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="31321-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="31321-103">В этом разделе описывается формат обязательное имя для файлов обновляемые сведения, Справка, известную как HelpInfo XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="31321-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="31321-104">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="31321-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="31321-105">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="31321-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="31321-106">Далее приведены элементы с именем.</span><span class="sxs-lookup"><span data-stu-id="31321-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="31321-107">ModuleName значение из **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.</span><span class="sxs-lookup"><span data-stu-id="31321-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="31321-108">ModuleGUID значение из **GUID** ключа в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="31321-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="31321-109">Например если имя модуля является «TestModule», идентификатор GUID модуля 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 бы имя XML-файл HelpInfo для модуля:</span><span class="sxs-lookup"><span data-stu-id="31321-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`