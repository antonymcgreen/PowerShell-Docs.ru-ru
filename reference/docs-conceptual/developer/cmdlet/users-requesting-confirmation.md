---
ms.date: 09/13/2016
ms.topic: reference
title: Запрос на подтверждение от пользователей
description: Запрос на подтверждение от пользователей
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646305"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="46452-103">Запрос на подтверждение от пользователей</span><span class="sxs-lookup"><span data-stu-id="46452-103">Users Requesting Confirmation</span></span>

<span data-ttu-id="46452-104">При указании значения `true` для `SupportsShouldProcess` параметра объявления атрибута командлета пользователи могут указать `Confirm` параметр в командной строке.</span><span class="sxs-lookup"><span data-stu-id="46452-104">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="46452-105">В среде по умолчанию пользователи могут указать `Confirm` параметр или `"-Confirm:$true` , чтобы подтверждение запрашивалось при вызове метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .</span><span class="sxs-lookup"><span data-stu-id="46452-105">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="46452-106">Это обходит запросы подтверждения [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , даже для операций с высоким уровнем влияния.</span><span class="sxs-lookup"><span data-stu-id="46452-106">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="46452-107">Если `Confirm` параметр не указан, вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение, если `$ConfirmPreference` привилегированная переменная равна или превышает `ConfirmImpact` значение параметра командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="46452-107">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="46452-108">Значение по умолчанию `$ConfirmPreference` — High.</span><span class="sxs-lookup"><span data-stu-id="46452-108">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="46452-109">Таким образом, в среде по умолчанию только командлеты и поставщики, которые задают подтверждение запроса на действие с высокой степенью влияния.</span><span class="sxs-lookup"><span data-stu-id="46452-109">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="46452-110">Если `Confirm` параметр имеет значение false или `"-Confirm:$false` указан, то вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) запрашивает подтверждение от пользователя, а `$ConfirmPreference` переменная оболочки игнорируется.</span><span class="sxs-lookup"><span data-stu-id="46452-110">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="46452-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="46452-111">Remarks</span></span>

- <span data-ttu-id="46452-112">Для командлетов и поставщиков, которые указывают `SupportsShouldProcess` , но не могут `ConfirmImpact` обрабатывать эти действия как действия "среднего влияния" и не запрашиваются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46452-112">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="46452-113">Их уровень влияния меньше значения по умолчанию для `$ConfirmPreference` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="46452-113">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="46452-114">Если пользователь указывает `Verbose` параметр, он будет уведомлен об операции, даже если они не запрашивают подтверждение.</span><span class="sxs-lookup"><span data-stu-id="46452-114">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="46452-115">См. также</span><span class="sxs-lookup"><span data-stu-id="46452-115">See Also</span></span>

[<span data-ttu-id="46452-116">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46452-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
