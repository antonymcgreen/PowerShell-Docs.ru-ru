---
title: Объявление атрибута ValidatePattern | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787807"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="ac477-102">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="ac477-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="ac477-103">Атрибут ValidatePattern указывает шаблон регулярного выражения, который проверяет аргумент параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="ac477-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="ac477-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac477-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="ac477-105">При вызове ValidatePattern в командлете среда выполнения Windows PowerShell преобразует аргумент параметра командлета в строку, а затем сравнивает эту строку с шаблоном, предоставленным атрибутом ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="ac477-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="ac477-106">Командлет выполняется только в том случае, если преобразованное строковое представление аргумента соответствует указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="ac477-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="ac477-107">Если они не совпадают, то среда выполнения Windows PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ac477-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac477-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac477-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="ac477-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac477-109">Parameters</span></span>

<span data-ttu-id="ac477-110">`RegexString`([System. String](/dotnet/api/System.String)) обязательный.</span><span class="sxs-lookup"><span data-stu-id="ac477-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="ac477-111">Задает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="ac477-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="ac477-112">Параметры ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="ac477-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="ac477-113">Задает побитовое сочетание флагов [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) , задающих параметры регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="ac477-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac477-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac477-114">Remarks</span></span>

- <span data-ttu-id="ac477-115">Этот атрибут можно использовать только один раз для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="ac477-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="ac477-116">`Option`Для дальнейшего определения шаблона можно использовать параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac477-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="ac477-117">Например, можно сделать шаблон чувствительным к регистру.</span><span class="sxs-lookup"><span data-stu-id="ac477-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="ac477-118">Если этот атрибут применяется к коллекции, каждый элемент в коллекции должен соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="ac477-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="ac477-119">Атрибут ValidatePattern определяется классом [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .</span><span class="sxs-lookup"><span data-stu-id="ac477-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac477-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ac477-120">See Also</span></span>

[<span data-ttu-id="ac477-121">System. Management. Automation. Валидатепаттернаттрибуте</span><span class="sxs-lookup"><span data-stu-id="ac477-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="ac477-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac477-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
