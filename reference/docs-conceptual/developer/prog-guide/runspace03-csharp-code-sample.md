---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода RunSpace03 (C#)
description: Пример кода RunSpace03 (C#)
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653843"
---
# <a name="runspace03-c-code-sample"></a>Пример кода RunSpace03 (C#)

Ниже приведен исходный код C# для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт». В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт. В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.

> [!NOTE]
> Исходный файл C# (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a>См. также:

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
