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
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="8f9ec-102">Пример кода AccessDbProviderSample02</span><span class="sxs-lookup"><span data-stu-id="8f9ec-102">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="8f9ec-103">В следующем коде показано реализации поставщика Windows PowerShell, описанные в [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).</span><span class="sxs-lookup"><span data-stu-id="8f9ec-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span> <span data-ttu-id="8f9ec-104">Эта реализация создает путь, подключается к базе данных Access и затем удаляет диск.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-104">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="8f9ec-105">Вы можете скачать C# исходный файл (AccessDBSampleProvider02.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-105">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="8f9ec-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="8f9ec-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="8f9ec-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="8f9ec-108">Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="8f9ec-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="8f9ec-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="8f9ec-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L11-L154 "AccessDBProviderSample02.cs")]


## <a name="see-also"></a><span data-ttu-id="8f9ec-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8f9ec-110">See Also</span></span>

[<span data-ttu-id="8f9ec-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9ec-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="8f9ec-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9ec-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)