---
ms.date: 09/12/2016
ms.topic: reference
title: Как проверить обновляемую справку
description: Как проверить обновляемую справку
ms.openlocfilehash: 47873089bfa1b918ea9970915e829a22aa7254c5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667629"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описываются подходы к тестированию обновляемой справки для модуля.

## <a name="using-verbose-to-detect-errors"></a>Использование verbose для обнаружения ошибок

После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** . Параметр **verbose** направляет сведения `Update-Help` о критических шагах в действиях, изчитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.

После разрешения всех подробных сообщений выполните `Update-Help` команду с параметром **Debug** .
Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.
