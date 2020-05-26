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
# <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

В этом разделе описывается требуемый формат имени для обновляемого CAB-файла справки (. CAB-файлы).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

Обновляемый CAB-файл (. CAB-файл) должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Ниже приведены элементы имени.

ModuleName значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .

Модулегуид значение ключа **GUID** в манифесте модуля.

UICulture язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле. Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.

Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
