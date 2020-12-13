---
ms.date: 09/13/2016
ms.topic: reference
title: Отображение сведений об ошибке
description: Отображение сведений об ошибке
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653060"
---
# <a name="displaying-error-information"></a><span data-ttu-id="e6bad-103">Отображение сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="e6bad-103">Displaying Error Information</span></span>

<span data-ttu-id="e6bad-104">В этом разделе обсуждаются способы, с помощью которых пользователи могут отображать сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e6bad-104">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="e6bad-105">При возникновении ошибки в командлете по умолчанию отображается представление сведений об ошибке, похожее на следующие выходные данные ошибки.</span><span class="sxs-lookup"><span data-stu-id="e6bad-105">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="e6bad-106">Однако пользователи могут просматривать ошибки по категориям, присвоив `$ErrorView` переменной значение `"CategoryView"` .</span><span class="sxs-lookup"><span data-stu-id="e6bad-106">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="e6bad-107">В представлении "Категория" отображаются конкретные сведения из записи об ошибке, а не описание ошибки в произвольном тексте.</span><span class="sxs-lookup"><span data-stu-id="e6bad-107">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="e6bad-108">Это представление может быть полезно, если имеется длинный список ошибок для проверки.</span><span class="sxs-lookup"><span data-stu-id="e6bad-108">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="e6bad-109">В представлении «Категория» предыдущее сообщение об ошибке отображается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e6bad-109">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="e6bad-110">Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="e6bad-110">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6bad-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6bad-111">See Also</span></span>

[<span data-ttu-id="e6bad-112">Записи об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bad-112">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="e6bad-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bad-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
