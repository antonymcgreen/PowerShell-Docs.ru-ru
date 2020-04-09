---
title: Пример кодаC#GetProc04 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 439ba3f3-91b1-46a4-8d07-9af6edb71bc4
caps.latest.revision: 5
ms.openlocfilehash: d17a67019b7451f2da5595b3258457a01cc86b0b
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978361"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="c2a98-102">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="c2a98-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="c2a98-103">В следующем коде показана реализация командлета `Get-Process`, который сообщает о неустранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="c2a98-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="c2a98-104">Эта реализация вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) для сообщения об устранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="c2a98-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="c2a98-105">Вы можете скачать C# исходный файл (getprov04.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="c2a98-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c2a98-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="c2a98-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="c2a98-107">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="c2a98-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c2a98-108">Образец кода</span><span class="sxs-lookup"><span data-stu-id="c2a98-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="c2a98-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="c2a98-109">See Also</span></span>

[<span data-ttu-id="c2a98-110">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2a98-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c2a98-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2a98-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
