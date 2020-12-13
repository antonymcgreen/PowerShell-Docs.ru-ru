---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода AccessDbProviderSample01
description: Пример кода AccessDbProviderSample01
ms.openlocfilehash: 5be593b9e86347b2f55de156fe4d9b44cfab5b78
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659415"
---
# <a name="accessdbprovidersample01-code-sample"></a>Пример кода AccessDbProviderSample01

В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).
Эта реализация предоставляет методы для запуска и остановки поставщика, хотя он не предоставляет средства для доступа к хранилищу данных или для получения или установки данных в хранилище данных, он предоставляет базовые функциональные возможности, необходимые для всех поставщиков.

> [!NOTE]
> Исходный файл C# (AccessDBSampleProvider01.cs) для этого поставщика можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге. Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a>См. также:

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
