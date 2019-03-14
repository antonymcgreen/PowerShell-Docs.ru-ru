---
title: Пример кода AccessDbProviderSample06 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baab6a56-c199-48d7-a03e-a904b1bb1baa
caps.latest.revision: 7
ms.openlocfilehash: 6e86318573df92b9ec84056631843e0efa096a3b
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795612"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="a71fd-102">Пример кода AccessDbProviderSample06</span><span class="sxs-lookup"><span data-stu-id="a71fd-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="a71fd-103">Следующий код показывает реализацию Windows PowerShell, описано в разделе поставщика содержимого [Создание поставщика Windows PowerShell содержимое](./creating-a-windows-powershell-content-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a71fd-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span> <span data-ttu-id="a71fd-104">Этот поставщик позволяет пользователю управлять содержимым элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="a71fd-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="a71fd-105">Вы можете скачать C# исходный файл (AccessDBSampleProvider06.cs) для данного поставщика, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="a71fd-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a71fd-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a71fd-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a71fd-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="a71fd-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="a71fd-108">Дополнительные сведения о других реализаций поставщика Windows PowerShell, см. в разделе [проектирование ваш поставщик PowerShell Windows](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a71fd-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="a71fd-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="a71fd-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="a71fd-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a71fd-110">See Also</span></span>

[<span data-ttu-id="a71fd-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a71fd-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a71fd-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a71fd-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)