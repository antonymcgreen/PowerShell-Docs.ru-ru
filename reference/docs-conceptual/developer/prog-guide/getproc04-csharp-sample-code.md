---
title: GetProc04 (C#) образец кода | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: dd3965ee504641b1b629ba203090ee14c670da43
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771895"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="3d9ee-102">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="3d9ee-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="3d9ee-103">В следующем коде показана реализация `Get-Process` командлета, который сообщает о неустранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="3d9ee-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="3d9ee-104">Эта реализация вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) для сообщения об устранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="3d9ee-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3d9ee-105">Исходный файл C# (getprov04.cs) для этого командлета Get-proc можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="3d9ee-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3d9ee-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="3d9ee-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3d9ee-107">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="3d9ee-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3d9ee-108">Образец кода</span><span class="sxs-lookup"><span data-stu-id="3d9ee-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="3d9ee-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3d9ee-109">See Also</span></span>

[<span data-ttu-id="3d9ee-110">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d9ee-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3d9ee-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d9ee-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
