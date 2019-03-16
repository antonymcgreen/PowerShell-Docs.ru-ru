---
title: Примеры кода GetProc04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 67081528ebe14fbb082091c1b9500de82069b48f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054651"
---
# <a name="getproc04-code-samples"></a>Примеры кода GetProc04

Ниже приведены примеры кода для командлета GetProc04 образца. Это `Get-Process` командлетов, которые описаны в [Добавление устранимые отчеты об ошибках Your командлету](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md). Это `Get-Process` вызывает командлет [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод всякий раз, когда возникает исключение недопустимой операции при получении сведений о процессе.

> [!NOTE]
> Вы можете скачать C# исходный файл (getprov04.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.

Полный пример кода см. в следующих разделах.

|Language|Раздел|
|--------------|-----------|
|C#|[GetProc04 (C#) пример кода](./getproc04-csharp-sample-code.md)|
|VB.NET|[GetProc04 образец кода (VB.NET)](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)