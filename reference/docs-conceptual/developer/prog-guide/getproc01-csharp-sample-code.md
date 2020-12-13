---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc01 (C#)
description: Пример кода GetProc01 (C#)
ms.openlocfilehash: 79509ff12afb32c907058f4ddb0c707f3823857a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654482"
---
# <a name="getproc01-c-sample-code"></a>Пример кода GetProc01 (C#)

В следующем коде показана реализация командлета Sample GetProc01. Обратите внимание, что командлет упрощается за счет выполнения фактической работы по получению процесса к методу [System. Diagnostics. Process.-Processing *](/dotnet/api/System.Diagnostics.Process.GetProcesses) .

> [!NOTE]
> Вы можете скачать исходный файл C# (getproc01.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a>См. также:

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
