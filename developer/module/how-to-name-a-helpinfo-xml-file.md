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
# <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

В этом разделе описывается формат обязательное имя для файлов обновляемые сведения, Справка, известную как HelpInfo XML-файлов.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

XML-файл HelpInfo должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Далее приведены элементы с именем.

ModuleName значение из **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.

ModuleGUID значение из **GUID** ключа в манифесте модуля.

Например если имя модуля является «TestModule», идентификатор GUID модуля 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 бы имя XML-файл HelpInfo для модуля:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`