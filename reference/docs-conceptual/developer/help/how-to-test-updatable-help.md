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
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811513"
---
# <a name="how-to-test-updatable-help"></a>Как проверить обновляемую справку

В этом разделе описываются подходы к тестированию обновляемой справки для модуля.

## <a name="using-verbose-to-detect-errors"></a>Использование verbose для обнаружения ошибок

После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** . Параметр **verbose** направляет сведения `Update-Help` о критических шагах в действиях, изчитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.

После разрешения всех подробных сообщений выполните `Update-Help` команду с параметром **Debug** . Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.
