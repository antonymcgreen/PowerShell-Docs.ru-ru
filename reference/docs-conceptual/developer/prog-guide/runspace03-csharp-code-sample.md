---
title: Пример кода RunSpace03 (C#) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: df34652f60ed85b13739a04485cf6622cf924872
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784798"
---
# <a name="runspace03-c-code-sample"></a>Пример кода RunSpace03 (C#)

Ниже приведен исходный код C# для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт». В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт. В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.

> [!NOTE]
> Исходный файл C# (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a>См. также

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
