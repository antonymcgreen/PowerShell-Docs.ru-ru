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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068289"
---
# <a name="displaying-error-information"></a><span data-ttu-id="28bb0-102">Отображение сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="28bb0-102">Displaying Error Information</span></span>

<span data-ttu-id="28bb0-103">В этом разделе обсуждаются способы, в котором пользователи могут отобразить сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="28bb0-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="28bb0-104">Когда командлета возникает ошибка, представление сведений об ошибке по умолчанию имеют следующие выходные данные ошибок.</span><span class="sxs-lookup"><span data-stu-id="28bb0-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="28bb0-105">Тем не менее, пользователи могут просматривать ошибки по категориям, задав `$ErrorView` переменной `"CategoryView"`.</span><span class="sxs-lookup"><span data-stu-id="28bb0-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="28bb0-106">Вид по категориям отображает специализированную информацию из запись об ошибке, а не произвольное текстовое описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="28bb0-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="28bb0-107">Это представление может быть полезно при наличии длинный список ошибок для сканирования.</span><span class="sxs-lookup"><span data-stu-id="28bb0-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="28bb0-108">В представлении по категориям ранее сообщения об ошибке отображается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="28bb0-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="28bb0-109">Дополнительные сведения о категориях ошибок см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="28bb0-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28bb0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="28bb0-110">See Also</span></span>

[<span data-ttu-id="28bb0-111">Записи об ошибках PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="28bb0-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="28bb0-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28bb0-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
