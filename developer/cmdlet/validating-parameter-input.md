---
title: Проверка входных данных параметра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.assetid: 3f15bf20-a068-4a7d-a170-bc43f755d1fe
caps.latest.revision: 14
ms.openlocfilehash: 171e3e974619e197a0bcc9dfc759297005e34568
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067150"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="19fe4-102">Проверка входных данных параметра</span><span class="sxs-lookup"><span data-stu-id="19fe4-102">Validating Parameter Input</span></span>

<span data-ttu-id="19fe4-103">PowerShell можно проверить аргументы, передаваемые параметры командлета несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="19fe4-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="19fe4-104">PowerShell можно проверить длину, диапазон и шаблон символов, аргумента.</span><span class="sxs-lookup"><span data-stu-id="19fe4-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="19fe4-105">Он может проверять количество доступных аргументов (число).</span><span class="sxs-lookup"><span data-stu-id="19fe4-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="19fe4-106">Эти правила проверки определяются атрибуты проверки, объявленные с атрибутом параметр на открытые свойства класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="19fe4-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="19fe4-107">Чтобы проверить аргумента параметра, среда выполнения PowerShell использует сведения, предоставляемые атрибуты проверки для подтвердить значение параметра, перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="19fe4-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="19fe4-108">Если входные данные параметра не является допустимым, то пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="19fe4-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="19fe4-109">Каждый параметр проверки определяет правило проверки, которое обеспечивается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fe4-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="19fe4-110">PowerShell соблюдает правила для проверки, на основе следующих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="19fe4-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="19fe4-111">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="19fe4-111">ValidateCount</span></span>

<span data-ttu-id="19fe4-112">Указывает минимальное и максимальное число аргументов, которые могут принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="19fe4-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="19fe4-113">Дополнительные сведения см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19fe4-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="19fe4-114">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="19fe4-114">ValidateLength</span></span>

<span data-ttu-id="19fe4-115">Указывает минимальное и максимальное число символов в качестве аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="19fe4-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="19fe4-116">Дополнительные сведения см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19fe4-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="19fe4-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="19fe4-117">ValidatePattern</span></span>

<span data-ttu-id="19fe4-118">Указывает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="19fe4-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="19fe4-119">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19fe4-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="19fe4-120">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="19fe4-120">ValidateRange</span></span>

<span data-ttu-id="19fe4-121">Задает минимальное и максимальное значения аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="19fe4-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="19fe4-122">Дополнительные сведения см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19fe4-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="19fe4-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="19fe4-123">ValidateSet</span></span>

<span data-ttu-id="19fe4-124">Указывает допустимые значения для параметра аргумента.</span><span class="sxs-lookup"><span data-stu-id="19fe4-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="19fe4-125">Дополнительные сведения см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19fe4-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19fe4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="19fe4-126">See Also</span></span>

[<span data-ttu-id="19fe4-127">Как проверки входных параметров</span><span class="sxs-lookup"><span data-stu-id="19fe4-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="19fe4-128">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fe4-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
