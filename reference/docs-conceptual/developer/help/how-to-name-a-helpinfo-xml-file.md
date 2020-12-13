---
ms.date: 09/12/2016
ms.topic: reference
title: Как назвать XML-файл HelpInfo
description: Как назвать XML-файл HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659044"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

XML-файл HelpInfo должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Ниже приведены элементы имени.

- `<ModuleName>` — Значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .

- `<ModuleGUID>` — Значение ключа **GUID** в манифесте модуля.

Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
