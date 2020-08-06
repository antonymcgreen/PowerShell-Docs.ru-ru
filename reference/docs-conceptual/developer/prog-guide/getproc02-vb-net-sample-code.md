---
title: Пример кода GetProc02 (VB.NET) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 98261f2d6678e24bb8e8df6d2c8a405b25203364
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787178"
---
# <a name="getproc02-vbnet-sample-code"></a>Пример кода GetProc02 (VB.NET)

В следующем коде показана реализация `Get-Process` командлета, который принимает входные данные командной строки. Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .

## <a name="code-sample"></a>Образец кода

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
