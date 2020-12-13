---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc04 (C#)
description: Пример кода GetProc04 (C#)
ms.openlocfilehash: 80020b60a7ab34caec0c856b9b7d12021f4276b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654374"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="f2b2e-103">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="f2b2e-103">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="f2b2e-104">В следующем коде показана реализация `Get-Process` командлета, который сообщает о неустранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="f2b2e-104">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="f2b2e-105">Эта реализация вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) для сообщения об устранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="f2b2e-105">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b2e-106">Вы можете скачать исходный файл C# (getprov04.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="f2b2e-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f2b2e-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="f2b2e-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="f2b2e-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="f2b2e-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f2b2e-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="f2b2e-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="f2b2e-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2b2e-110">See Also</span></span>

[<span data-ttu-id="f2b2e-111">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2b2e-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f2b2e-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2b2e-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
