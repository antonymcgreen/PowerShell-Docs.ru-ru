---
title: Пользователи, запрашивающие подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: ed9ff9fc1668a89e1ac0ceac8f0800a15b349226
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369253"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="c15d9-102">Запрос на подтверждение от пользователей</span><span class="sxs-lookup"><span data-stu-id="c15d9-102">Users Requesting Confirmation</span></span>

<span data-ttu-id="c15d9-103">При указании значения `true` для параметра `SupportsShouldProcess` в объявлении атрибута командлета пользователи могут указать параметр `Confirm` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c15d9-103">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="c15d9-104">В среде по умолчанию пользователи могут указать параметр `Confirm` или `"-Confirm:$true`, чтобы подтверждение запрашивалось при вызове метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .</span><span class="sxs-lookup"><span data-stu-id="c15d9-104">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="c15d9-105">Это обходит запросы подтверждения [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , даже для операций с высоким уровнем влияния.</span><span class="sxs-lookup"><span data-stu-id="c15d9-105">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="c15d9-106">Если `Confirm` не указан, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение, если переменная предпочтений `$ConfirmPreference` больше или равна значению параметра `ConfirmImpact` командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="c15d9-106">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="c15d9-107">Значение по умолчанию `$ConfirmPreference` — High.</span><span class="sxs-lookup"><span data-stu-id="c15d9-107">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="c15d9-108">Таким образом, в среде по умолчанию только командлеты и поставщики, которые задают подтверждение запроса на действие с высокой степенью влияния.</span><span class="sxs-lookup"><span data-stu-id="c15d9-108">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="c15d9-109">Если `Confirm` имеет значение false или если задано `"-Confirm:$false`, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение от пользователя, а переменная оболочки `$ConfirmPreference` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c15d9-109">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="c15d9-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="c15d9-110">Remarks</span></span>

- <span data-ttu-id="c15d9-111">Для командлетов и поставщиков, которые задают `SupportsShouldProcess`, но не `ConfirmImpact`, эти действия обрабатываются как действия "среднего влияния" и не запрашиваются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c15d9-111">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="c15d9-112">Их уровень влияния меньше значения по умолчанию для привилегированной переменной `$ConfirmPreference`.</span><span class="sxs-lookup"><span data-stu-id="c15d9-112">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="c15d9-113">Если пользователь указывает параметр `Verbose`, он будет уведомлен об этой операции, даже если у них нет запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="c15d9-113">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c15d9-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c15d9-114">See Also</span></span>

[<span data-ttu-id="c15d9-115">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c15d9-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
