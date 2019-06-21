---
title: GetProc02 образец кода (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3497546-5b3a-4e29-84ba-cd9747be64b3
caps.latest.revision: 6
ms.openlocfilehash: 4ec63ed32bd2906f5b027523aa0f253b51a5d873
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67301350"
---
# <a name="getproc02-vbnet-sample-code"></a>Пример кода GetProc02 (VB.NET)

Следующий код показывает реализацию `Get-Process` командлет, который принимает входные данные командной строки. Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий входные данные командной строки и он использует [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) метод как механизм выходные данные для отправки выходных данных в объекты конвейер.

## <a name="code-sample"></a>Пример кода

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
