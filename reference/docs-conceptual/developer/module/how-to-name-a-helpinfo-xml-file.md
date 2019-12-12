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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367203"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

В этом разделе описывается требуемый формат имени для обновляемых файлов справки, которые обычно называются XML-файлами HelpInfo.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Как назвать XML-файл HelpInfo

XML-файл HelpInfo должен иметь имя в следующем формате.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Ниже приведены элементы имени.

ModuleName значение свойства **Name** объекта **ModuleInfo** , возвращаемого командлетом [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) .

Модулегуид значение ключа **GUID** в манифесте модуля.

Например, если имя модуля — "Тестмодуле", а GUID модуля — 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, то имя XML-файла HelpInfo для модуля будет выглядеть следующим образом:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`