---
title: Способы тестирования обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794269"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описаны подходы к тестированию обновляемую справку для модуля.

## <a name="using-verbose-to-detect-errors"></a>С помощью подробного для обнаружения ошибок

После отправки XML-файл HelpInfo и CAB-файлы для вашего модуля, проверить файлы, запустив [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с **Verbose** параметра. **Verbose** параметр направляет `Update-Help` сообщить о важных этапов его действия, от чтения **HelpInfoUri** ключа в манифесте модуля к проверке типов файлов в распакованную CAB-файл и поместить файлы в каталоге модуля для конкретного языка.

При разрешении все подробные сообщения, запустите `Update-Help` с **Отладка** параметра. Этот параметр определяет всех оставшихся проблем с обновляемых файлов справки.