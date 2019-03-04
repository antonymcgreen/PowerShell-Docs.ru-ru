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
# <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

В этом разделе описывается формат обязательное имя для файлов обновляемые сведения, Справка, известную как HelpInfo XML-файлов.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

XML-файл HelpInfo должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Далее приведены элементы с именем.

ModuleName значение из **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.
Значение **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.

ModuleGUID значение из **GUID** ключа в манифесте модуля.

Например если имя модуля является «TestModule», идентификатор GUID модуля 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 бы имя XML-файл HelpInfo для модуля:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`