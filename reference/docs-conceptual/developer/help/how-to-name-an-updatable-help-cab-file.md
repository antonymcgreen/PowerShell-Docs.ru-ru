---
title: Как назвать CAB-файл обновляемой справки
ms.date: 09/12/2016
ms.openlocfilehash: 42486461d92f1f6fcff452a4539edf5be7a66f22
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893005"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

В этом разделе описывается требуемый формат имени для обновляемых файлов CAB-файла справки ( `.CAB` ).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Как назвать CAB-файл обновляемой справки

Обновляемый файл CAB ( `.CAB` ) должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Ниже приведены элементы имени.

- `<ModuleName>`— Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .
- `<ModuleGUID>`— Значение ключа **GUID** в манифесте модуля.
- `<UICulture>`— Язык и региональные параметры пользовательского интерфейса файлов справки в CAB-файле. Это значение должно соответствовать значению одного из элементов **UICulture** в XML-файле HelpInfo для модуля.

Например, если имя модуля — "Тестмодуле", идентификатор GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, а язык и региональные параметры пользовательского интерфейса — "en-US", имя файла CAB будет выглядеть следующим образом:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
