---
title: Типы файлов, разрешенные в обновляемом CAB-файле справки | Документация Майкрософт
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 6e9e51a50226430465726d27874e02e98ee67672
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560990"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>Типы файлов, которые могут использоваться в CAB-файле обновляемой справки

В этом разделе перечислены и описаны требования к содержимому для обновляемых CAB-файлов справки.

## <a name="updatable-help-cab-file-requirements"></a>Требования к обновляемому CAB-файлу справки

Несжатое содержимое CAB-файла по умолчанию ограничено 1 ГБ. Чтобы обойти это ограничение, пользователям необходимо использовать параметр **Force** командлетов [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .

Для обеспечения безопасности файлов справки, загружаемых из Интернета, обновляемый CAB-файл справки может включать только перечисленные ниже типы файлов. Командлет [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет все файлы по схемам разделов справки. Если `Update-Help` командлет встречает файл, который является недопустимым или не является разрешенным типом, он не устанавливает недопустимый файл и прекращает установку файлов из CAB-файла на компьютере пользователя.

- Разделы справки на основе XML для командлетов.

- Разделы справки на основе XML для скриптов и функций.

- Разделы справки на основе XML для поставщиков Windows PowerShell.

- Разделы справки на основе текста, например о разделах.

[Обновление — Справка](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла при его распаковке. Если `Update-Help` находит несовместимые типы файлов в обновляемом CAB-файле справки, он создает завершающую ошибку и останавливает операцию. Он не устанавливает файлы справки из CAB-файла, даже для соответствующих типов файлов.
