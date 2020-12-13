---
ms.date: 09/13/2016
ms.topic: reference
title: Проверка входных данных параметра
description: Проверка входных данных параметра
ms.openlocfilehash: a97b5c670e8c36463a85bbef1506f6311bdd5ec3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660398"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="19293-103">Проверка входных данных параметра</span><span class="sxs-lookup"><span data-stu-id="19293-103">Validating Parameter Input</span></span>

<span data-ttu-id="19293-104">PowerShell может проверить аргументы, передаваемые в параметры командлета, несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="19293-104">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="19293-105">PowerShell может проверить длину, диапазон и шаблон символов аргумента.</span><span class="sxs-lookup"><span data-stu-id="19293-105">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="19293-106">Он может проверить количество доступных аргументов (количество).</span><span class="sxs-lookup"><span data-stu-id="19293-106">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="19293-107">Эти правила проверки определяются атрибутами проверки, объявленными с атрибутом Parameter в общих свойствах класса командлета.</span><span class="sxs-lookup"><span data-stu-id="19293-107">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="19293-108">Для проверки аргумента параметра среда выполнения PowerShell использует сведения, предоставленные атрибутами проверки, для подтверждения значения параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="19293-108">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="19293-109">Если входные данные параметра недопустимы, пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="19293-109">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="19293-110">Каждый параметр проверки определяет правило проверки, принудительно применяемое PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19293-110">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="19293-111">PowerShell применяет правила проверки на основе следующих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="19293-111">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="19293-112">валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="19293-112">ValidateCount</span></span>

<span data-ttu-id="19293-113">Указывает минимальное и максимальное число аргументов, которые может принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="19293-113">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="19293-114">Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19293-114">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="19293-115">валидателенгс</span><span class="sxs-lookup"><span data-stu-id="19293-115">ValidateLength</span></span>

<span data-ttu-id="19293-116">Указывает минимальное и максимальное число символов в аргументе параметра.</span><span class="sxs-lookup"><span data-stu-id="19293-116">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="19293-117">Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19293-117">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="19293-118">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="19293-118">ValidatePattern</span></span>

<span data-ttu-id="19293-119">Задает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="19293-119">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="19293-120">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19293-120">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="19293-121">валидатеранже</span><span class="sxs-lookup"><span data-stu-id="19293-121">ValidateRange</span></span>

<span data-ttu-id="19293-122">Задает минимальное и максимальное значения аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="19293-122">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="19293-123">Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="19293-123">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="19293-124">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="19293-124">ValidateSet</span></span>

<span data-ttu-id="19293-125">Указывает допустимые значения для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="19293-125">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="19293-126">Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".</span><span class="sxs-lookup"><span data-stu-id="19293-126">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19293-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="19293-127">See Also</span></span>

[<span data-ttu-id="19293-128">Как проверить входные параметры</span><span class="sxs-lookup"><span data-stu-id="19293-128">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="19293-129">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19293-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
