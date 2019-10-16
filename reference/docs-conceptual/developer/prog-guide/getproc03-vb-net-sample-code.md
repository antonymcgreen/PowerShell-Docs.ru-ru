---
title: Пример кода GetProc03 (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff94c452-d4ec-4492-ac20-61ad52f8ae8c
caps.latest.revision: 7
ms.openlocfilehash: a0a88ca517347a94fc81534caace6efa0f13fdd7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360313"
---
# <a name="getproc03-vbnet-sample-code"></a>Пример кода GetProc03 (VB.NET)

В следующем коде показана реализация командлета `Get-Process`, который может принимать конвейерные входные данные. Эта реализация определяет параметр `Name`, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве результата. механизм отправки объектов в конвейер.

## <a name="code-sample"></a>Пример кода

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
