---
title: Пример кода RunSpace07 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784713"
---
# <a name="runspace07-code-sample"></a>Примеры кода RunSpace07

Ниже приведен исходный код для примера Runspace07, описанного в разделе [Создание консольного приложения, добавляющего команды в конвейер](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).
Этот пример приложения создает пространство выполнения, создает конвейер, добавляет в конвейер две команды, а затем выполняет конвейер. Команды, добавленные в конвейер, — `Get-Process` это `Measure-Object` командлеты и.

> [!NOTE]
> Исходный файл C# (runspace07.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a>См. также

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
