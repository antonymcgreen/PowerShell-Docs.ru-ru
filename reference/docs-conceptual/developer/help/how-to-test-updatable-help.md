---
title: Как проверить обновляемую справку
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892971"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описываются подходы к тестированию обновляемой справки для модуля.

## <a name="using-verbose-to-detect-errors"></a>Использование verbose для обнаружения ошибок

После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** . Параметр **verbose** направляет сведения `Update-Help` о критических шагах в действиях, изчитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.

После разрешения всех подробных сообщений выполните `Update-Help` команду с параметром **Debug** .
Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.
