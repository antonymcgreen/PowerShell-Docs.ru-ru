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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860510"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="a116b-102">Псевдонимы командлета</span><span class="sxs-lookup"><span data-stu-id="a116b-102">Cmdlet Aliases</span></span>

<span data-ttu-id="a116b-103">Чтобы улучшить взаимодействие с пользователем командлет можно использовать псевдонимы командлетов.</span><span class="sxs-lookup"><span data-stu-id="a116b-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="a116b-104">Можно добавить псевдонимы для часто используемых командлетов для уменьшения объема ввода и позвольте проще выполнять задачи быстрее.</span><span class="sxs-lookup"><span data-stu-id="a116b-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="a116b-105">Вы можете включить встроенные псевдонимы в командлеты, или пользователи могут определять свои собственные пользовательских псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="a116b-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="a116b-106">Например [Get-Command](/powershell/module/microsoft.powershell.core/get-command) командлет имеет встроенный `gcm` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a116b-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="a116b-107">Псевдонимы также можно добавлять имена команд из других языков, чтобы пользователи не имеют дополнительные новые команды.</span><span class="sxs-lookup"><span data-stu-id="a116b-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="a116b-108">Рекомендации по псевдоним</span><span class="sxs-lookup"><span data-stu-id="a116b-108">Alias Guidelines</span></span>

<span data-ttu-id="a116b-109">При создании встроенных псевдонимов для командлетов, придерживайтесь следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="a116b-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="a116b-110">Прежде чем назначить псевдонимы, запустите Windows PowerShell, а затем запустите [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) командлет, чтобы просмотреть псевдонимы, которые уже используются.</span><span class="sxs-lookup"><span data-stu-id="a116b-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="a116b-111">Включать префикс псевдоним, который ссылается на команды имя командлета и суффикс псевдоним, ссылающийся на существительное имени командлета.</span><span class="sxs-lookup"><span data-stu-id="a116b-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="a116b-112">Например, псевдоним `Import-Module` командлет является «ipmo».</span><span class="sxs-lookup"><span data-stu-id="a116b-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="a116b-113">Список всех команд и их псевдонимы, см. в разделе [глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="a116b-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="a116b-114">Для командлетов, которые имеют ту же команду включать один и тот же префикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="a116b-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="a116b-115">Например псевдонимы для всех командлетов Windows PowerShell с глаголом «Get» в имени используйте префикс «g».</span><span class="sxs-lookup"><span data-stu-id="a116b-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="a116b-116">Для командлетов, которые содержат же существительное Включите один и тот же суффикс псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a116b-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="a116b-117">Например псевдонимы для всех командлетов Windows PowerShell, которые содержат существительное «Сеанс» в имени используйте суффикс «sn».</span><span class="sxs-lookup"><span data-stu-id="a116b-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="a116b-118">Для командлетов, которые эквивалентны команды на других языках используйте имя команды.</span><span class="sxs-lookup"><span data-stu-id="a116b-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="a116b-119">Как правило сделать псевдонимов, как можно более короткими.</span><span class="sxs-lookup"><span data-stu-id="a116b-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="a116b-120">Убедитесь, что псевдоним имеет хотя бы один символ, уникальных для команды и один символ, уникальных для существительное.</span><span class="sxs-lookup"><span data-stu-id="a116b-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="a116b-121">Добавьте дополнительные символы, при необходимости, чтобы сделать псевдоним уникальным.</span><span class="sxs-lookup"><span data-stu-id="a116b-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="a116b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a116b-122">See Also</span></span>

[<span data-ttu-id="a116b-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a116b-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
