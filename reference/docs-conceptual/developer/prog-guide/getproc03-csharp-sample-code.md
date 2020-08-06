---
title: GetProc03 (C#) образец кода | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 278c3f36bb975f9ea195978853e6539c0bd15084
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787127"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="5f05d-102">Пример кода GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="5f05d-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="5f05d-103">В следующем коде показана реализация `Get-Process` командлета, который может принимать конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="5f05d-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="5f05d-104">Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе предоставляемых имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве механизма вывода для отправки объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="5f05d-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="5f05d-105">Исходный файл C# (getprov03.cs) для этого командлета Get-proc можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="5f05d-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="5f05d-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="5f05d-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="5f05d-107">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="5f05d-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5f05d-108">Образец кода</span><span class="sxs-lookup"><span data-stu-id="5f05d-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="5f05d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5f05d-109">See Also</span></span>

[<span data-ttu-id="5f05d-110">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f05d-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5f05d-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f05d-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
