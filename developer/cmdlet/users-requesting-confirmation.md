---
title: Пользователи с запросом на подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: e4abbb14b31406b845d9b6af6b6372338fb0d926
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856240"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="3dd53-102">Запрос на подтверждение от пользователей</span><span class="sxs-lookup"><span data-stu-id="3dd53-102">Users Requesting Confirmation</span></span>

<span data-ttu-id="3dd53-103">При указании параметра `true` для `SupportsShouldProcess` параметра в объявлении атрибута командлет, пользователи могут указать `Confirm` параметр в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3dd53-103">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="3dd53-104">В среде по умолчанию, пользователи могут указать `Confirm` параметр или `"-Confirm:$true` таким образом, запрашивается подтверждение при [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="3dd53-104">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="3dd53-105">Это позволяет обойти [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запросов подтверждения, даже для операций с высоким уровнем влияния.</span><span class="sxs-lookup"><span data-stu-id="3dd53-105">This bypasses [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="3dd53-106">Если `Confirm` не указан, [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов запрашивает подтверждение, если `$ConfirmPreference` привилегированной переменной равно или больше, чем `ConfirmImpact` параметр командлет или поставщика.</span><span class="sxs-lookup"><span data-stu-id="3dd53-106">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="3dd53-107">Значение по умолчанию `$ConfirmPreference` — высокий.</span><span class="sxs-lookup"><span data-stu-id="3dd53-107">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="3dd53-108">Таким образом в среде по умолчанию, только командлеты и поставщики, укажите действие качественные запросит подтверждение.</span><span class="sxs-lookup"><span data-stu-id="3dd53-108">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="3dd53-109">Если `Confirm` имеет значение false или если `"-Confirm:$false` указано, [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов запрашивает подтверждение от пользователя и `$ConfirmPreference` переменной оболочки учитывается.</span><span class="sxs-lookup"><span data-stu-id="3dd53-109">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="3dd53-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="3dd53-110">Remarks</span></span>

- <span data-ttu-id="3dd53-111">Для командлеты и поставщики, которые указывают `SupportsShouldProcess`, но не `ConfirmImpact`, эти действия будут обрабатываться как действия «со средним уровнем влияния», и они не будут запрашивать по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3dd53-111">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="3dd53-112">Их уровень влияния меньше, чем значение по умолчанию `$ConfirmPreference` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="3dd53-112">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="3dd53-113">Если пользователь указывает `Verbose` параметра, они будут уведомлены о операции, даже если они не запрашивается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="3dd53-113">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3dd53-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3dd53-114">See Also</span></span>

[<span data-ttu-id="3dd53-115">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3dd53-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
