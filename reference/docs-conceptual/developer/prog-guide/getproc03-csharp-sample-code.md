---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc03 (C#)
description: Пример кода GetProc03 (C#)
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355584"
---
# <a name="getproc03-c-sample-code"></a>Пример кода GetProc03 (C#)

В следующем коде показана реализация `Get-Process` командлета, который может принимать конвейерные входные данные. Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе предоставляемых имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве механизма вывода для отправки объектов в конвейер.

> [!NOTE]
> Вы можете скачать исходный файл C# (getprov03.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a>См. также:

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
