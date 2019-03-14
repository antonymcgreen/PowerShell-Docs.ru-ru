---
title: Том, какое имя CAB-файл обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: 0b58d5ee19a85bed26bc6549ced48b890cd62f64
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794763"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

В этом разделе описывается формат обязательное имя CAB-файл обновляемой справки (. Файлы CAB-файла).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

Обновляемые CAB-файл (. Файл CAB) должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Далее приведены элементы с именем.

ModuleName значение из **имя** свойство **ModuleInfo** объекта, [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлетом.

ModuleGUID значение из **GUID** ключа в манифесте модуля.

Культура пользовательского интерфейса UICulture файлы справки в CAB-файл. Это значение должно соответствовать значение одного из **UICulture** элементов в XML-файл HelpInfo для модуля.

Например если имя модуля «TestModule», идентификатор GUID модуля 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 и язык и региональные параметры пользовательского интерфейса — «en US», имя CAB-файл будет иметь:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`