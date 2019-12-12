---
title: Проверка входных параметров | Документация Майкрософт
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363513"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="fa882-102">Проверка входных данных параметра</span><span class="sxs-lookup"><span data-stu-id="fa882-102">Validating Parameter Input</span></span>

<span data-ttu-id="fa882-103">PowerShell может проверить аргументы, передаваемые в параметры командлета, несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="fa882-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="fa882-104">PowerShell может проверить длину, диапазон и шаблон символов аргумента.</span><span class="sxs-lookup"><span data-stu-id="fa882-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="fa882-105">Он может проверить количество доступных аргументов (количество).</span><span class="sxs-lookup"><span data-stu-id="fa882-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="fa882-106">Эти правила проверки определяются атрибутами проверки, объявленными с атрибутом Parameter в общих свойствах класса командлета.</span><span class="sxs-lookup"><span data-stu-id="fa882-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="fa882-107">Для проверки аргумента параметра среда выполнения PowerShell использует сведения, предоставленные атрибутами проверки, для подтверждения значения параметра перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="fa882-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="fa882-108">Если входные данные параметра недопустимы, пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fa882-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="fa882-109">Каждый параметр проверки определяет правило проверки, принудительно применяемое PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa882-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="fa882-110">PowerShell применяет правила проверки на основе следующих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="fa882-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="fa882-111">валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="fa882-111">ValidateCount</span></span>

<span data-ttu-id="fa882-112">Указывает минимальное и максимальное число аргументов, которые может принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="fa882-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="fa882-113">Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="fa882-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="fa882-114">валидателенгс</span><span class="sxs-lookup"><span data-stu-id="fa882-114">ValidateLength</span></span>

<span data-ttu-id="fa882-115">Указывает минимальное и максимальное число символов в аргументе параметра.</span><span class="sxs-lookup"><span data-stu-id="fa882-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="fa882-116">Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="fa882-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="fa882-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="fa882-117">ValidatePattern</span></span>

<span data-ttu-id="fa882-118">Задает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="fa882-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="fa882-119">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="fa882-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="fa882-120">валидатеранже</span><span class="sxs-lookup"><span data-stu-id="fa882-120">ValidateRange</span></span>

<span data-ttu-id="fa882-121">Задает минимальное и максимальное значения аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="fa882-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="fa882-122">Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="fa882-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="fa882-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="fa882-123">ValidateSet</span></span>

<span data-ttu-id="fa882-124">Указывает допустимые значения для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="fa882-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="fa882-125">Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".</span><span class="sxs-lookup"><span data-stu-id="fa882-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa882-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa882-126">See Also</span></span>

[<span data-ttu-id="fa882-127">Проверка входных параметров</span><span class="sxs-lookup"><span data-stu-id="fa882-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="fa882-128">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa882-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
