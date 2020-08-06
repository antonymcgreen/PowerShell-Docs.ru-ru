---
title: Псевдонимы командлетов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: fed4055f09e01c5f3fa87584d48551918606f4eb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784543"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="96619-102">Псевдонимы командлета</span><span class="sxs-lookup"><span data-stu-id="96619-102">Cmdlet Aliases</span></span>

<span data-ttu-id="96619-103">Псевдонимы командлетов можно использовать для улучшения взаимодействия с пользователем командлета.</span><span class="sxs-lookup"><span data-stu-id="96619-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="96619-104">Можно добавлять псевдонимы к часто используемым командлетам, чтобы сократить число операций ввода и упростить процесс быстрого завершения задач.</span><span class="sxs-lookup"><span data-stu-id="96619-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="96619-105">В командлеты можно включать встроенные псевдонимы, а пользователи могут определять собственные пользовательские псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="96619-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="96619-106">Например, командлет [Get-Command](/powershell/module/microsoft.powershell.core/get-command) имеет встроенный `gcm` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="96619-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="96619-107">Можно также использовать псевдонимы для добавления имен команд из других языков, чтобы пользователям не нужно было изучать новые команды.</span><span class="sxs-lookup"><span data-stu-id="96619-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="96619-108">Рекомендации по псевдонимам</span><span class="sxs-lookup"><span data-stu-id="96619-108">Alias Guidelines</span></span>

<span data-ttu-id="96619-109">При создании встроенных псевдонимов для командлетов следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="96619-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="96619-110">Прежде чем приступать к назначению псевдонимов, запустите Windows PowerShell, а затем выполните командлет [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) , чтобы просмотреть уже используемые псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="96619-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="96619-111">Включите префикс псевдонима, который ссылается на глагол имени командлета, и суффикс псевдонима, который ссылается на существительное с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="96619-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="96619-112">Например, псевдонимом для `Import-Module` командлета является IPMO.</span><span class="sxs-lookup"><span data-stu-id="96619-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="96619-113">Список всех команд и их псевдонимов см. в разделе [команды командлета](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="96619-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="96619-114">Для командлетов, имеющих одну и ту же команду, следует включить один и тот же префикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="96619-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="96619-115">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых есть команда Get, используют префикс g.</span><span class="sxs-lookup"><span data-stu-id="96619-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="96619-116">Для командлетов, имеющих одинаковые существительные, включите один и тот же суффикс псевдонима.</span><span class="sxs-lookup"><span data-stu-id="96619-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="96619-117">Например, псевдонимы для всех командлетов Windows PowerShell, в имени которых имеется существительное "Session", используют суффикс "SN".</span><span class="sxs-lookup"><span data-stu-id="96619-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="96619-118">Для командлетов, эквивалентных командам на других языках, используйте имя команды.</span><span class="sxs-lookup"><span data-stu-id="96619-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="96619-119">Как правило, псевдонимы должны быть как можно более короткими.</span><span class="sxs-lookup"><span data-stu-id="96619-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="96619-120">Убедитесь, что псевдоним содержит по крайней мере один отдельный символ для команды и один отдельный символ для существительного.</span><span class="sxs-lookup"><span data-stu-id="96619-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="96619-121">При необходимости добавьте дополнительные символы, чтобы сделать псевдоним уникальным.</span><span class="sxs-lookup"><span data-stu-id="96619-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="96619-122">См. также</span><span class="sxs-lookup"><span data-stu-id="96619-122">See Also</span></span>

[<span data-ttu-id="96619-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96619-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
