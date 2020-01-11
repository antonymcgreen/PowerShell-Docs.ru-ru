---
title: Пример кода RunSpace05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: 8802e308712be93992ead5ef77b97d8c21b137f7
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870648"
---
# <a name="runspace05-code-sample"></a>Примеры кода RunSpace05

Ниже приведен исходный код для примера Runspace05, описанный в разделе [Настройка пространства выполнения с помощью рунспацеконфигуратион](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).
В этом примере показано, как создать сведения о конфигурации пространства выполнения, создать пространство выполнения, создать конвейер с помощью одной команды, а затем выполнить конвейер. Выполняемая команда является командлетом `Get-Process`.

> [!NOTE]
> C# Исходный файл (runspace05.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.

## <a name="code-sample"></a>Образец кода

[!code-csharp[Runspace05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a>См. также

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
