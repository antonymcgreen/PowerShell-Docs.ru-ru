---
title: Отображение сведений об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369973"
---
# <a name="displaying-error-information"></a><span data-ttu-id="c425a-102">Отображение сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="c425a-102">Displaying Error Information</span></span>

<span data-ttu-id="c425a-103">В этом разделе обсуждаются способы, с помощью которых пользователи могут отображать сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c425a-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="c425a-104">При возникновении ошибки в командлете по умолчанию отображается представление сведений об ошибке, похожее на следующие выходные данные ошибки.</span><span class="sxs-lookup"><span data-stu-id="c425a-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="c425a-105">Однако пользователи могут просматривать ошибки по категориям, присвоив переменной `$ErrorView` значение `"CategoryView"`.</span><span class="sxs-lookup"><span data-stu-id="c425a-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="c425a-106">В представлении "Категория" отображаются конкретные сведения из записи об ошибке, а не описание ошибки в произвольном тексте.</span><span class="sxs-lookup"><span data-stu-id="c425a-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="c425a-107">Это представление может быть полезно, если имеется длинный список ошибок для проверки.</span><span class="sxs-lookup"><span data-stu-id="c425a-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="c425a-108">В представлении «Категория» предыдущее сообщение об ошибке отображается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c425a-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="c425a-109">Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="c425a-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c425a-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="c425a-110">See Also</span></span>

[<span data-ttu-id="c425a-111">Записи об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c425a-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="c425a-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c425a-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
