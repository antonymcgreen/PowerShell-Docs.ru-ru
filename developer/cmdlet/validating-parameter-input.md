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
ms.openlocfilehash: f7e5d4fb2f89bd6bc7036fdcff8f38e017d5d0e4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858850"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="dc900-102">Проверка входных данных параметра</span><span class="sxs-lookup"><span data-stu-id="dc900-102">Validating Parameter Input</span></span>

<span data-ttu-id="dc900-103">Windows PowerShell можно проверить аргументы, передаваемые параметры командлета несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="dc900-103">Windows PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span> <span data-ttu-id="dc900-104">Windows PowerShell можно проверить длину, диапазон и шаблон символов, аргумента.</span><span class="sxs-lookup"><span data-stu-id="dc900-104">Windows PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span> <span data-ttu-id="dc900-105">Он может проверять количество доступных аргументов (число).</span><span class="sxs-lookup"><span data-stu-id="dc900-105">It can validate the number of arguments available (the count).</span></span> <span data-ttu-id="dc900-106">Эти правила проверки определяются атрибуты проверки, объявленные с атрибутом параметр на открытые свойства класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dc900-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="dc900-107">Чтобы проверить аргумент параметра, среды выполнения Windows PowerShell использует сведения, предоставляемые атрибуты проверки для подтверждения значение параметра, перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="dc900-107">To validate a parameter argument, the Windows PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span> <span data-ttu-id="dc900-108">Если входные данные параметра не является допустимым, то пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dc900-108">If the parameter input is not valid, the user receives an error message.</span></span> <span data-ttu-id="dc900-109">Каждый параметр проверки определяет правила проверки, которое зависит от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc900-109">Each validation parameter defines a validation rule that is enforced by Windows PowerShell.</span></span>

<span data-ttu-id="dc900-110">Windows PowerShell обеспечивает выполнение правил проверки, на основе следующих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="dc900-110">Windows PowerShell enforces the validation rules based on the following attributes.</span></span>

<span data-ttu-id="dc900-111">ValidateCount указывает минимальное и максимальное число аргументов, которые могут принимать параметр.</span><span class="sxs-lookup"><span data-stu-id="dc900-111">ValidateCount Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span> <span data-ttu-id="dc900-112">Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc900-112">For more information about the syntax used to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

<span data-ttu-id="dc900-113">ValidateLength указывает минимальное и максимальное число символов в качестве аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="dc900-113">ValidateLength Specifies the minimum and maximum number of characters in the parameter argument.</span></span> <span data-ttu-id="dc900-114">Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc900-114">For more information about the syntax used to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

<span data-ttu-id="dc900-115">ValidatePattern задает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="dc900-115">ValidatePattern Specifies a regular expression that validates the parameter argument.</span></span> <span data-ttu-id="dc900-116">Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc900-116">For more information about the syntax used to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

<span data-ttu-id="dc900-117">ValidateRange задает минимальное и максимальное значения аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="dc900-117">ValidateRange Specifies the minimum and maximum values of the parameter argument.</span></span> <span data-ttu-id="dc900-118">Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc900-118">For more information about the syntax used to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

<span data-ttu-id="dc900-119">ValidateSet указывает допустимые значения для параметра аргумента.</span><span class="sxs-lookup"><span data-stu-id="dc900-119">ValidateSet Specifies the valid values for the parameter argument.</span></span> <span data-ttu-id="dc900-120">Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc900-120">For more information about the syntax used to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc900-121">См. также</span><span class="sxs-lookup"><span data-stu-id="dc900-121">See Also</span></span>

[<span data-ttu-id="dc900-122">Как проверки входных параметров</span><span class="sxs-lookup"><span data-stu-id="dc900-122">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="dc900-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc900-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
