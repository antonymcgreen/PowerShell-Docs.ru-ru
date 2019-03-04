---
title: Типы файлов, допустимые в обновляемый файл CAB-файла справки | Документация Майкрософт
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
ms.openlocfilehash: 931383858c0b83f0a9a66026c215e16481b89e9e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862840"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>Типы файлов, которые могут использоваться в CAB-файле обновляемой справки

В этом разделе перечислены и описаны требований к содержимому для обновляемой справки CAB-файлов.

## <a name="updatable-help-cab-file-requirements"></a>Требования к CAB-файл обновляемой справки

По умолчанию несжатого содержимого файла CAB-файлов ограничен 1 ГБ. Чтобы обойти это ограничение, пользователи должны использовать **Force** параметр [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлетов.
По умолчанию несжатого содержимого файла CAB-файлов ограничен 1 ГБ. Чтобы обойти это ограничение, пользователи должны использовать **Force** параметр [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлетов.

Чтобы обеспечить безопасность файлов справки, загруженных из Интернета, обновляемой справки CAB-файл можно включить только типы файлов, перечисленных ниже. [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) командлет проверяет все файлы по схемам раздела справки. Если `Update-Help` командлет обнаружил файл, который является недопустимым или не является типом разрешенных, он не устанавливает недопустимый файл и останавливает установке файлов из CAB-файла на компьютере пользователя.
Чтобы обеспечить безопасность файлов справки, загруженных из Интернета, обновляемой справки CAB-файл можно включить только типы файлов, перечисленных ниже. [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) командлет проверяет все файлы по схемам раздела справки. Если `Update-Help` командлет обнаружил файл, который является недопустимым или не является типом разрешенных, он не устанавливает недопустимый файл и останавливает установке файлов из CAB-файла на компьютере пользователя.

- Основанный на XML разделы справки по командлетам.

- Основанный на XML разделы справки по сценариям и функциям.

- Основанный на XML разделы справки по поставщикам Windows PowerShell.

- Текстовый разделы справки, таких как разделы справки по модулю.

[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла, когда он распаковывает CAB. Если `Update-Help` находит файл несовместимые типы в обновляемой справки CAB-файл, он создает неустранимую ошибку и останавливает операцию. Он не устанавливает файлы справки из CAB-файла, даже те файл, совместимый типов.
[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла, когда он распаковывает CAB. Если `Update-Help` находит файл несовместимые типы в обновляемой справки CAB-файл, он создает неустранимую ошибку и останавливает операцию. Он не устанавливает файлы справки из CAB-файла, даже те файл, совместимый типов.