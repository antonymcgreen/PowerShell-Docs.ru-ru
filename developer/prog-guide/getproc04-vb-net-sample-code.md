---
title: GetProc04 образец кода (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d22f47b-3679-4587-a559-94454415d2dd
caps.latest.revision: 5
ms.openlocfilehash: 0d0d1a3f82bc2cee025139d69fee02eb601fa563
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055467"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="b8e15-102">Пример кода GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="b8e15-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="b8e15-103">Следующий код показывает реализацию `Get-Process` командлет, который сообщает устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="b8e15-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="b8e15-104">Такая реализация вызывает [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="b8e15-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="b8e15-105">Вы можете скачать C# исходный файл (getprov04.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="b8e15-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b8e15-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b8e15-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b8e15-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="b8e15-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b8e15-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="b8e15-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="b8e15-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b8e15-109">See Also</span></span>

[<span data-ttu-id="b8e15-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8e15-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b8e15-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8e15-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)