---
title: Пример кодаC#Runspace01 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 39e7d49b51942da51a581ab33dbe46ab848ca1c3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366643"
---
# <a name="runspace01-c-code-sample"></a>Пример кода Runspace01 (C#)

Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program). Для этого приложение вызывает пространство выполнения, а затем вызывает команду. (Обратите внимание, что это приложение не указывает сведения о конфигурации пространства выполнения и не создает конвейер явным образом). Вызываемая команда является командлетом `Get-Process`.

> [!NOTE]
> Вы можете скачать C# исходный файл (runspace01.cs) для этого пространства выполнения с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a>См. также:

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
