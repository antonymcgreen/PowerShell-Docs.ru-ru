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
ms.openlocfilehash: a3e8ae664d5c0e29d0f84174950bebe6a1da6a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857830"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="a494e-102">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="a494e-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="a494e-103">В этом разделе описывается формат обязательное имя для файлов обновляемые сведения, Справка, известную как HelpInfo XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="a494e-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="a494e-104">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="a494e-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="a494e-105">XML-файл HelpInfo должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="a494e-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="a494e-106">Далее приведены элементы с именем.</span><span class="sxs-lookup"><span data-stu-id="a494e-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="a494e-107">ModuleName значение из **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.</span><span class="sxs-lookup"><span data-stu-id="a494e-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
<span data-ttu-id="a494e-108">Значение **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.</span><span class="sxs-lookup"><span data-stu-id="a494e-108">The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="a494e-109">ModuleGUID значение из **GUID** ключа в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="a494e-109">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="a494e-110">Например если имя модуля является «TestModule», идентификатор GUID модуля 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 бы имя XML-файл HelpInfo для модуля:</span><span class="sxs-lookup"><span data-stu-id="a494e-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`