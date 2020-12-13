---
ms.date: 09/12/2016
ms.topic: reference
title: Как назвать CAB-файл обновляемой справки
description: Как назвать CAB-файл обновляемой справки
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658922"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

В этом разделе описывается требуемый формат имени для обновляемых файлов CAB-файла справки ( `.CAB` ).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

Обновляемый файл CAB ( `.CAB` ) должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Ниже приведены элементы имени.

- `<ModuleName>` — Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .
- `<ModuleGUID>` — Значение ключа **GUID** в манифесте модуля.
- `<UICulture>` — Язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле. Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.

Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
