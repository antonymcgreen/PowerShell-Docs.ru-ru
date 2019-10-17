---
title: Проверка обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367153"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описываются подходы к тестированию обновляемой справки для модуля.

## <a name="using-verbose-to-detect-errors"></a>Использование verbose для обнаружения ошибок

После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** . Параметр **verbose** направляет `Update-Help` для получения сведений о критических шагах в действиях, от считывания ключа **HelpInfoUri** в манифесте модуля для проверки типов файлов в распакованном CAB-файле и поместив файлы в соответствующий язык. Каталог модуля.

После разрешения всех подробных сообщений выполните команду `Update-Help` с параметром **Debug** . Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.