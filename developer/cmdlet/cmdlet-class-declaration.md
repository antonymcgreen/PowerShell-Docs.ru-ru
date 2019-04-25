---
title: Объявление класса Cmdlet | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], declaring
- declaring cmdlets [PowerShell SDK]
ms.assetid: 1fcc4c5e-0c75-496c-a712-5f844e310576
caps.latest.revision: 14
ms.openlocfilehash: 3168275423dc65fcb2e41dedd9bea275ede58397
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068646"
---
# <a name="cmdlet-class-declaration"></a><span data-ttu-id="804e5-102">Объявление класса командлета</span><span class="sxs-lookup"><span data-stu-id="804e5-102">Cmdlet Class Declaration</span></span>

<span data-ttu-id="804e5-103">Microsoft .NET Framework класс объявляется как командлет, указав **командлет** атрибут как метаданные для класса.</span><span class="sxs-lookup"><span data-stu-id="804e5-103">A Microsoft .NET Framework class is declared as a cmdlet by specifying the **Cmdlet** attribute as metadata for the class.</span></span> <span data-ttu-id="804e5-104">( **Командлет** атрибут является единственным обязательным атрибутом для всех командлетов).</span><span class="sxs-lookup"><span data-stu-id="804e5-104">(The **Cmdlet** attribute is the only required attribute for all cmdlets).</span></span> <span data-ttu-id="804e5-105">При указании **командлет** атрибут, необходимо указать пару глагол и существительное, которая идентифицирует командлет, чтобы пользователь.</span><span class="sxs-lookup"><span data-stu-id="804e5-105">When you specify the **Cmdlet** attribute, you must specify the verb-and-noun pair that identifies the cmdlet to the user.</span></span> <span data-ttu-id="804e5-106">И необходимо описать функциональные возможности Windows PowerShell, командлет будет поддерживать.</span><span class="sxs-lookup"><span data-stu-id="804e5-106">And, you must describe the Windows PowerShell functionality that the cmdlet supports.</span></span> <span data-ttu-id="804e5-107">Дополнительные сведения о синтаксисе объявления, который используется для указания **командлет** атрибут, см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="804e5-107">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

> [!NOTE]
> <span data-ttu-id="804e5-108">**Командлет** определяется атрибут [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="804e5-108">The **Cmdlet** attribute is defined by the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) class.</span></span> <span data-ttu-id="804e5-109">Свойства этого класса соответствуют параметрам объявления, которые используются при объявлении атрибута.</span><span class="sxs-lookup"><span data-stu-id="804e5-109">The properties of this class correspond to the declaration parameters that are used when you declare the attribute.</span></span>

## <a name="nouns"></a><span data-ttu-id="804e5-110">Существительные</span><span class="sxs-lookup"><span data-stu-id="804e5-110">Nouns</span></span>

<span data-ttu-id="804e5-111">Существительное командлета указывает ресурсы, на которых работает командлет.</span><span class="sxs-lookup"><span data-stu-id="804e5-111">The noun of the cmdlet specifies the resources upon which the cmdlet acts.</span></span> <span data-ttu-id="804e5-112">Существительное отличает командлеты от других командлетов.</span><span class="sxs-lookup"><span data-stu-id="804e5-112">The noun differentiates your cmdlets from other cmdlets.</span></span>

<span data-ttu-id="804e5-113">Существительные в имена командлетов должно быть специфичные и в случае универсальных существительные *server*, лучше всего добавить короткий префикс, который отличает ресурса от другие аналогичные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="804e5-113">Nouns in cmdlet names must be specific, and in the case of generic nouns, such as *server*, it is best to add a short prefix that differentiates your resource from other similar resources.</span></span> <span data-ttu-id="804e5-114">Например, имя командлета, который включает в себя существительное с префиксом является `Get-SQLServer`.</span><span class="sxs-lookup"><span data-stu-id="804e5-114">For example, a cmdlet name that includes a noun with a prefix is `Get-SQLServer`.</span></span> <span data-ttu-id="804e5-115">Комбинация существительного с более общими глагола позволяет пользователю быстро найти командлет, ее действие, а затем определите командлет его ресурсом, избегая ненужных командлет имя дублирования.</span><span class="sxs-lookup"><span data-stu-id="804e5-115">The combination of a specific noun with a more general verb enables the user to quickly locate the cmdlet by its action and then identify the cmdlet by its resource while avoiding unnecessary cmdlet name duplication.</span></span>

<span data-ttu-id="804e5-116">Список специальных символов, которые нельзя использовать в имена командлетов, см. в разделе [необходимые рекомендации по разработке](./required-development-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="804e5-116">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="verbs"></a><span data-ttu-id="804e5-117">Команды</span><span class="sxs-lookup"><span data-stu-id="804e5-117">Verbs</span></span>

<span data-ttu-id="804e5-118">При указании команды, рекомендации по разработке требуют использования одной из предопределенных команд, предоставляемых Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="804e5-118">When you specify a verb, the development guidelines require you to use one of the predefined verbs provided by Windows PowerShell.</span></span> <span data-ttu-id="804e5-119">С помощью одного из этих стандартных команд, вы должны гарантировать согласованность командлетов и командлеты, которые записываются корпорацией Майкрософт и другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="804e5-119">By using one of these predefined verbs, you will ensure consistency between the cmdlets that you write and the cmdlets that are written by Microsoft and by others.</span></span> <span data-ttu-id="804e5-120">Например команду «Get» используется для командлетов, получения данных.</span><span class="sxs-lookup"><span data-stu-id="804e5-120">For example, the "Get" verb is used for cmdlets that retrieve data.</span></span>

<span data-ttu-id="804e5-121">Дополнительные сведения о рекомендациях по для команд, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="804e5-121">For more information about guidelines for verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span> <span data-ttu-id="804e5-122">Список специальных символов, которые нельзя использовать в имена командлетов, см. в разделе [необходимые рекомендации по разработке](./required-development-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="804e5-122">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="supporting-windows-powershell-functionality"></a><span data-ttu-id="804e5-123">Вспомогательные функции Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="804e5-123">Supporting Windows PowerShell Functionality</span></span>

<span data-ttu-id="804e5-124">**Командлет** атрибут также позволяет указать, что командлет поддерживает некоторые функциональные возможности, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="804e5-124">The **Cmdlet** attribute also allows you to specify that your cmdlet supports some of the common functionality that is provided by Windows PowerShell.</span></span> <span data-ttu-id="804e5-125">Сюда входят поддержка общие функциональные возможности, такие как подтверждение отзыв пользователя (называется поддержку функции ShouldProcess) и поддержка транзакций.</span><span class="sxs-lookup"><span data-stu-id="804e5-125">This includes support for common functionality such as user feedback confirmation (referred to as support for the ShouldProcess feature) and support for transactions.</span></span> <span data-ttu-id="804e5-126">(Поддержка транзакций был введен в Windows PowerShell 2.0).</span><span class="sxs-lookup"><span data-stu-id="804e5-126">(Support for transactions was introduced in Windows PowerShell 2.0).</span></span>

<span data-ttu-id="804e5-127">Дополнительные сведения о синтаксисе объявления, который используется для указания **командлет** атрибут, см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="804e5-127">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="cmdlet-class-definition"></a><span data-ttu-id="804e5-128">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="804e5-128">Cmdlet Class Definition</span></span>

<span data-ttu-id="804e5-129">Следующий код является определение класса командлета GetProc.</span><span class="sxs-lookup"><span data-stu-id="804e5-129">The following code is the definition for a GetProc cmdlet class.</span></span> <span data-ttu-id="804e5-130">Обратите внимание на то, что Pascal, используется и что имя класса включает глагол и существительное командлета.</span><span class="sxs-lookup"><span data-stu-id="804e5-130">Notice that Pascal casing is used and that the name of the class includes the verb and noun of the cmdlet.</span></span>

[!code-csharp[GetProcessSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L33-L34 "GetProcessSample01.cs")]

## <a name="pascal-casing"></a><span data-ttu-id="804e5-131">Регистра Pascal</span><span class="sxs-lookup"><span data-stu-id="804e5-131">Pascal Casing</span></span>

<span data-ttu-id="804e5-132">При вводе имени командлеты, используйте Pascal регистр.</span><span class="sxs-lookup"><span data-stu-id="804e5-132">When you name cmdlets, use Pascal casing.</span></span> <span data-ttu-id="804e5-133">Например `Get-Item` и `Get-ItemProperty` командлеты Показать правильный способ использования регистра символов при именовании командлетов.</span><span class="sxs-lookup"><span data-stu-id="804e5-133">For example, the `Get-Item` and `Get-ItemProperty` cmdlets show the correct way to use capitalization when you are naming cmdlets.</span></span>

## <a name="see-also"></a><span data-ttu-id="804e5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="804e5-134">See Also</span></span>

[<span data-ttu-id="804e5-135">System.Management.Automation.CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="804e5-135">System.Management.Automation.CmdletAttribute</span></span>](/dotnet/api/System.Management.Automation.CmdletAttribute)

[<span data-ttu-id="804e5-136">Объявление CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="804e5-136">CmdletAttribute Declaration</span></span>](./cmdlet-attribute-declaration.md)

[<span data-ttu-id="804e5-137">Командлет глаголов</span><span class="sxs-lookup"><span data-stu-id="804e5-137">Cmdlet Verb Names</span></span>](./approved-verbs-for-windows-powershell-commands.md)

[<span data-ttu-id="804e5-138">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="804e5-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="804e5-139">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="804e5-139">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
