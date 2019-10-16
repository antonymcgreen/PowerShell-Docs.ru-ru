---
title: Псевдонимы командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369983"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="ffc6d-102">Псевдонимы командлета</span><span class="sxs-lookup"><span data-stu-id="ffc6d-102">Cmdlet Aliases</span></span>

<span data-ttu-id="ffc6d-103">Псевдонимы командлетов можно использовать для улучшения взаимодействия с пользователем командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="ffc6d-104">Можно добавлять псевдонимы к часто используемым командлетам, чтобы сократить число операций ввода и упростить процесс быстрого завершения задач.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="ffc6d-105">В командлеты можно включать встроенные псевдонимы, а пользователи могут определять собственные пользовательские псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="ffc6d-106">Например, командлет [Get-Command](/powershell/module/microsoft.powershell.core/get-command) имеет встроенный псевдоним `gcm`.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="ffc6d-107">Можно также использовать псевдонимы для добавления имен команд из других языков, чтобы пользователям не нужно было изучать новые команды.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="ffc6d-108">Рекомендации по псевдонимам</span><span class="sxs-lookup"><span data-stu-id="ffc6d-108">Alias Guidelines</span></span>

<span data-ttu-id="ffc6d-109">При создании встроенных псевдонимов для командлетов следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="ffc6d-110">Прежде чем приступать к назначению псевдонимов, запустите Windows PowerShell, а затем выполните командлет [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) , чтобы просмотреть уже используемые псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="ffc6d-111">Включите префикс псевдонима, который ссылается на глагол имени командлета, и суффикс псевдонима, который ссылается на существительное с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="ffc6d-112">Например, псевдоним для командлета `Import-Module` — IPMO.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="ffc6d-113">Список всех команд и их псевдонимов см. в разделе [команды командлета](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="ffc6d-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="ffc6d-114">Для командлетов, имеющих одну и ту же команду, следует включить один и тот же префикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="ffc6d-115">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых есть команда Get, используют префикс g.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="ffc6d-116">Для командлетов, имеющих одинаковые существительные, включите один и тот же суффикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="ffc6d-117">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых имеется существительное "Session", используют суффикс "SN".</span><span class="sxs-lookup"><span data-stu-id="ffc6d-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="ffc6d-118">Для командлетов, эквивалентных командам на других языках, используйте имя команды.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="ffc6d-119">Как правило, псевдонимы должны быть как можно более короткими.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="ffc6d-120">Убедитесь, что псевдоним содержит по крайней мере один отдельный символ для команды и один отдельный символ для существительного.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="ffc6d-121">При необходимости добавьте дополнительные символы, чтобы сделать псевдоним уникальным.</span><span class="sxs-lookup"><span data-stu-id="ffc6d-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffc6d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ffc6d-122">See Also</span></span>

[<span data-ttu-id="ffc6d-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffc6d-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
