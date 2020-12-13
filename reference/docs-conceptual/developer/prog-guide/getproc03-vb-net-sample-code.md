---
ms.date: 09/12/2016
ms.topic: reference
title: Пример кода GetProc03 (VB.NET)
description: Пример кода GetProc03 (VB.NET)
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355567"
---
# <a name="getproc03-vbnet-sample-code"></a>Пример кода GetProc03 (VB.NET)

В следующем коде показана реализация `Get-Process` командлета, который может принимать конвейерные входные данные. Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе предоставляемых имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве механизма вывода для отправки объектов в конвейер.

## <a name="code-sample"></a>Образец кода

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
