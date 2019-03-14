---
title: Пример кода AccessDbProviderSample02 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b89a4903-3efc-4b08-9b20-2baadf1d1b66
caps.latest.revision: 6
ms.openlocfilehash: 67a169bfac0b0fc90e6ccd276d3d3592d1b70bb0
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795493"
---
# <a name="accessdbprovidersample02-code-sample"></a>Пример кода AccessDbProviderSample02

В следующем коде показано реализации поставщика Windows PowerShell, описанные в [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md). Эта реализация создает путь, подключается к базе данных Access и затем удаляет диск.

> [!NOTE]
> Вы можете скачать C# исходный файл (AccessDBSampleProvider02.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.
>
> Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Пример кода

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L11-L154 "AccessDBProviderSample02.cs")]


## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)