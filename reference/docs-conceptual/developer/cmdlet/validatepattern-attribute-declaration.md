---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidatePattern
description: Объявление атрибута ValidatePattern
ms.openlocfilehash: 364f63d2c52563eaefe64bcbb2bbae511bccb074
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646173"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="07b14-103">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="07b14-103">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="07b14-104">Атрибут ValidatePattern указывает шаблон регулярного выражения, который проверяет аргумент параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="07b14-104">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="07b14-105">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07b14-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="07b14-106">При вызове ValidatePattern в командлете среда выполнения Windows PowerShell преобразует аргумент параметра командлета в строку, а затем сравнивает эту строку с шаблоном, предоставленным атрибутом ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="07b14-106">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="07b14-107">Командлет выполняется только в том случае, если преобразованное строковое представление аргумента соответствует указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="07b14-107">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="07b14-108">Если они не совпадают, то среда выполнения Windows PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="07b14-108">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="07b14-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07b14-109">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="07b14-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="07b14-110">Parameters</span></span>

<span data-ttu-id="07b14-111">`RegexString` ([System. String](/dotnet/api/System.String)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="07b14-111">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="07b14-112">Задает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="07b14-112">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="07b14-113">Параметры ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="07b14-113">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="07b14-114">Задает побитовое сочетание флагов [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) , задающих параметры регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="07b14-114">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="07b14-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="07b14-115">Remarks</span></span>

- <span data-ttu-id="07b14-116">Этот атрибут можно использовать только один раз для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="07b14-116">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="07b14-117">`Option`Для дальнейшего определения шаблона можно использовать параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="07b14-117">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="07b14-118">Например, можно сделать шаблон чувствительным к регистру.</span><span class="sxs-lookup"><span data-stu-id="07b14-118">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="07b14-119">Если этот атрибут применяется к коллекции, каждый элемент в коллекции должен соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="07b14-119">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="07b14-120">Атрибут ValidatePattern определяется классом [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .</span><span class="sxs-lookup"><span data-stu-id="07b14-120">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="07b14-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="07b14-121">See Also</span></span>

[<span data-ttu-id="07b14-122">System. Management. Automation. Валидатепаттернаттрибуте</span><span class="sxs-lookup"><span data-stu-id="07b14-122">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="07b14-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07b14-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
