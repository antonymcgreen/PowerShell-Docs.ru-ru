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
ms.openlocfilehash: 22cfbc63bd369ebcb2fd8a0d0e8d1995941bbb0f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74418002"
---
# <a name="accessdbprovidersample01-code-sample"></a>Пример кода AccessDbProviderSample01

В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md). Эта реализация предоставляет методы для запуска и остановки поставщика, хотя он не предоставляет средства для доступа к хранилищу данных или для получения или установки данных в хранилище данных, он предоставляет базовые функциональные возможности, необходимые для всех поставщиков.

> [!NOTE]
> C# Исходный файл (AccessDBSampleProvider01.cs) для этого поставщика можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
>
> Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.
>
> Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Образец кода

[!code-csharp[AccessDBProviderSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a>См. также:

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
