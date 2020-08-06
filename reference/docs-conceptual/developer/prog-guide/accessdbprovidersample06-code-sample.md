---
title: Пример кода AccessDbProviderSample06 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: f650648320a0a31324af1bd1a112f01bdfc6c599
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787246"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="0e488-102">Пример кода AccessDbProviderSample06</span><span class="sxs-lookup"><span data-stu-id="0e488-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="0e488-103">В следующем коде показана реализация поставщика содержимого Windows PowerShell, описанного в статье [Создание поставщика содержимого Windows PowerShell](./creating-a-windows-powershell-content-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0e488-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span>
<span data-ttu-id="0e488-104">Этот поставщик позволяет пользователю управлять содержимым элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="0e488-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="0e488-105">Исходный файл C# (AccessDBSampleProvider06.cs) для этого поставщика можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="0e488-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="0e488-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="0e488-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="0e488-107">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="0e488-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="0e488-108">Дополнительные сведения о других реализациях поставщиков Windows PowerShell см. в разделе [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0e488-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="0e488-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="0e488-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="0e488-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e488-110">See Also</span></span>

[<span data-ttu-id="0e488-111">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e488-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="0e488-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e488-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
