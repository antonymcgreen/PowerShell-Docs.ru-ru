---
title: Пример кода RunSpace08 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784696"
---
# <a name="runspace08-code-sample"></a>Примеры кода RunSpace08

Ниже приведен исходный код для примера Runspace08, описанного в разделе [Создание консольного приложения, добавляющего в команду Параметры](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).
Этот пример приложения создает пространство выполнения, создает конвейер, добавляет две команды в конвейер, добавляет два параметра во вторую команду, а затем выполняет конвейер. Команды, добавляемые в конвейер, — это `Get-Process` `Sort-Object` командлеты и.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
