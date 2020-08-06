---
title: Отображение сведений об ошибках | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774581"
---
# <a name="displaying-error-information"></a><span data-ttu-id="c7654-102">Отображение сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="c7654-102">Displaying Error Information</span></span>

<span data-ttu-id="c7654-103">В этом разделе обсуждаются способы, с помощью которых пользователи могут отображать сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c7654-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="c7654-104">При возникновении ошибки в командлете по умолчанию отображается представление сведений об ошибке, похожее на следующие выходные данные ошибки.</span><span class="sxs-lookup"><span data-stu-id="c7654-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="c7654-105">Однако пользователи могут просматривать ошибки по категориям, присвоив `$ErrorView` переменной значение `"CategoryView"` .</span><span class="sxs-lookup"><span data-stu-id="c7654-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="c7654-106">В представлении "Категория" отображаются конкретные сведения из записи об ошибке, а не описание ошибки в произвольном тексте.</span><span class="sxs-lookup"><span data-stu-id="c7654-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="c7654-107">Это представление может быть полезно, если имеется длинный список ошибок для проверки.</span><span class="sxs-lookup"><span data-stu-id="c7654-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="c7654-108">В представлении «Категория» предыдущее сообщение об ошибке отображается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c7654-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="c7654-109">Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="c7654-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7654-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c7654-110">See Also</span></span>

[<span data-ttu-id="c7654-111">Записи об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7654-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="c7654-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7654-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
