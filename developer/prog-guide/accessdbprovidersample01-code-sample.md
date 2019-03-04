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
ms.openlocfilehash: 01b95e18794501c2aff13d1e51b7400ae6fb8730
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859670"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="1fd15-102">Пример кода AccessDbProviderSample01</span><span class="sxs-lookup"><span data-stu-id="1fd15-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="1fd15-103">В следующем коде показано реализации поставщика Windows PowerShell, описанные в [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1fd15-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="1fd15-104">Эта реализация предоставляет методы для запуска и остановки поставщик, и несмотря на то, что она предоставляет средства для доступа к хранилищу данных или для получения или задания данные в хранилище данных, он предоставляет основные функциональные возможности, которые требуются для всех поставщиков.</span><span class="sxs-lookup"><span data-stu-id="1fd15-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="1fd15-105">Вы можете скачать C# исходный файл (AccessDBSampleProvider01.cs) для данного поставщика, с помощью Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="1fd15-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="1fd15-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="1fd15-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="1fd15-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="1fd15-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="1fd15-108">Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1fd15-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="1fd15-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="1fd15-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="1fd15-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1fd15-110">See Also</span></span>

[<span data-ttu-id="1fd15-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fd15-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="1fd15-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fd15-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)