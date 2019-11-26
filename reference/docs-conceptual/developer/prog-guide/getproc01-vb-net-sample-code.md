---
title: Пример кода GetProc01 (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ee87f67-6d2c-48cc-b300-3ae917c6dc88
caps.latest.revision: 5
ms.openlocfilehash: 80f145da8f4e2f3a39b1cdd533478b7fdc2f0a31
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417443"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="4b33a-102">Пример кода GetProc01 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="4b33a-102">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="4b33a-103">В следующем коде показана реализация командлета Sample GetProc01.</span><span class="sxs-lookup"><span data-stu-id="4b33a-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="4b33a-104">Обратите внимание, что командлет упрощается за счет выполнения фактической работы по получению процесса к методу [System. Diagnostics. Process.-Processing \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="4b33a-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="4b33a-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="4b33a-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="4b33a-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="4b33a-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="4b33a-107">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="4b33a-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="4b33a-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="4b33a-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="4b33a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4b33a-109">See Also</span></span>

[<span data-ttu-id="4b33a-110">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b33a-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="4b33a-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b33a-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
