---
ms.date: 09/13/2016
ms.topic: reference
title: Псевдонимы командлета
description: Псевдонимы командлета
ms.openlocfilehash: 734553a9911aef256df563afa6abcdb23d7a62e6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660788"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="ec61d-103">Псевдонимы командлета</span><span class="sxs-lookup"><span data-stu-id="ec61d-103">Cmdlet Aliases</span></span>

<span data-ttu-id="ec61d-104">Псевдонимы командлетов можно использовать для улучшения взаимодействия с пользователем командлета.</span><span class="sxs-lookup"><span data-stu-id="ec61d-104">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="ec61d-105">Можно добавлять псевдонимы к часто используемым командлетам, чтобы сократить число операций ввода и упростить процесс быстрого завершения задач.</span><span class="sxs-lookup"><span data-stu-id="ec61d-105">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="ec61d-106">В командлеты можно включать встроенные псевдонимы, а пользователи могут определять собственные пользовательские псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="ec61d-106">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="ec61d-107">Например, командлет [Get-Command](/powershell/module/microsoft.powershell.core/get-command) имеет встроенный `gcm` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="ec61d-107">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="ec61d-108">Можно также использовать псевдонимы для добавления имен команд из других языков, чтобы пользователям не нужно было изучать новые команды.</span><span class="sxs-lookup"><span data-stu-id="ec61d-108">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="ec61d-109">Рекомендации по псевдонимам</span><span class="sxs-lookup"><span data-stu-id="ec61d-109">Alias Guidelines</span></span>

<span data-ttu-id="ec61d-110">При создании встроенных псевдонимов для командлетов следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="ec61d-110">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="ec61d-111">Прежде чем приступать к назначению псевдонимов, запустите Windows PowerShell, а затем выполните командлет [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) , чтобы просмотреть уже используемые псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="ec61d-111">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="ec61d-112">Включите префикс псевдонима, который ссылается на глагол имени командлета, и суффикс псевдонима, который ссылается на существительное с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="ec61d-112">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="ec61d-113">Например, псевдонимом для `Import-Module` командлета является IPMO.</span><span class="sxs-lookup"><span data-stu-id="ec61d-113">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="ec61d-114">Список всех команд и их псевдонимов см. в разделе [команды командлета](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="ec61d-114">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="ec61d-115">Для командлетов, имеющих одну и ту же команду, следует включить один и тот же префикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ec61d-115">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="ec61d-116">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых есть команда Get, используют префикс g.</span><span class="sxs-lookup"><span data-stu-id="ec61d-116">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="ec61d-117">Для командлетов, имеющих одинаковые существительные, включите один и тот же суффикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ec61d-117">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="ec61d-118">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых имеется существительное "Session", используют суффикс "SN".</span><span class="sxs-lookup"><span data-stu-id="ec61d-118">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="ec61d-119">Для командлетов, эквивалентных командам на других языках, используйте имя команды.</span><span class="sxs-lookup"><span data-stu-id="ec61d-119">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="ec61d-120">Как правило, псевдонимы должны быть как можно более короткими.</span><span class="sxs-lookup"><span data-stu-id="ec61d-120">In general, make aliases as short as possible.</span></span> <span data-ttu-id="ec61d-121">Убедитесь, что псевдоним содержит по крайней мере один отдельный символ для команды и один отдельный символ для существительного.</span><span class="sxs-lookup"><span data-stu-id="ec61d-121">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="ec61d-122">При необходимости добавьте дополнительные символы, чтобы сделать псевдоним уникальным.</span><span class="sxs-lookup"><span data-stu-id="ec61d-122">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec61d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ec61d-123">See Also</span></span>

[<span data-ttu-id="ec61d-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec61d-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
