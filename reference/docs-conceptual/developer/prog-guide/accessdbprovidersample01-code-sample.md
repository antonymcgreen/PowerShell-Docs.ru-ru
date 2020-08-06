---
title: Пример кода AccessDbProviderSample01 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2e9f81b3011ea1b27bafd9e02ea7e0faf7903a62
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784832"
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
