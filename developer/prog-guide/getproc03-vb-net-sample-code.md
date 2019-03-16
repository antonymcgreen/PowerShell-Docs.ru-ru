---
title: GetProc03 образец кода (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff94c452-d4ec-4492-ac20-61ad52f8ae8c
caps.latest.revision: 7
ms.openlocfilehash: 0cfb5c203c97a4d20e7fadf8183e608e9e31b881
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058255"
---
# <a name="getproc03-vbnet-sample-code"></a>Пример кода GetProc03 (VB.NET)

Следующий код показывает реализацию `Get-Process` командлет, который может принять конвейерная входных данных. Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе на локальном компьютере, на основе предоставленных имен, а затем использует [System.Management.Automation.Cmdlet.WriteObject% 28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) метод в качестве механизма выходные данные для отправки объекты в конвейер.

## <a name="code-sample"></a>Пример кода

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->