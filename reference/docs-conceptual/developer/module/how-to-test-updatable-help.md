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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367153"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описываются подходы к тестированию обновляемой справки для модуля.

## <a name="using-verbose-to-detect-errors"></a>Использование verbose для обнаружения ошибок

После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** . Параметр **verbose** направляет `Update-Help`, чтобы сообщить о критических шагах в действиях, прочитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.

После разрешения всех подробных сообщений выполните команду `Update-Help` с параметром **Debug** . Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.