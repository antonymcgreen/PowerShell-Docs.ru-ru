---
title: Пример кода AccessDbProviderSample01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35540d2a-c18f-4179-b869-1a3dc5a8c1bd
caps.latest.revision: 6
ms.openlocfilehash: 429339a86b44bfa53302329fe1e21f6f91c52b42
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360553"
---
# <a name="accessdbprovidersample01-code-sample"></a>Пример кода AccessDbProviderSample01

В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Эта реализация предоставляет методы для запуска и остановки поставщика, хотя он не предоставляет средства для доступа к хранилищу данных или для получения или установки данных в хранилище данных, он предоставляет базовые функциональные возможности, необходимые для всех поставщиков.

> [!NOTE]
> C# Исходный файл (AccessDBSampleProvider01.cs) для этого поставщика можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Пример кода

[!code-csharp[AccessDBProviderSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a>См. также:

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
