---
title: Объявление атрибута ValidatePattern | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858880"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="d3597-102">Объявление атрибута ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="d3597-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="d3597-103">Атрибут ValidatePattern указывает шаблон регулярного выражения, проверяет корректность аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="d3597-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="d3597-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3597-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="d3597-105">При вызове командлета ValidatePattern, среда выполнения Windows PowerShell Преобразует аргумент параметра командлета в строку и затем сравнивает эту строку в шаблоне, указанного в атрибуте ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="d3597-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="d3597-106">Командлет выполняется только в том случае, если преобразованное строковое представление аргумента и указанному шаблону соответствует.</span><span class="sxs-lookup"><span data-stu-id="d3597-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="d3597-107">Если они не совпадают, сообщение об ошибке средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3597-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3597-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3597-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="d3597-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3597-109">Parameters</span></span>

<span data-ttu-id="d3597-110">`RegexString` ([System.String](/dotnet/api/System.String)) требуется.</span><span class="sxs-lookup"><span data-stu-id="d3597-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="d3597-111">Указывает регулярное выражение, которое проверяет аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="d3597-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="d3597-112">Параметры ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="d3597-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="d3597-113">Задает побитовое сочетание [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) флаги, определяющие параметры регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="d3597-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3597-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="d3597-114">Remarks</span></span>

- <span data-ttu-id="d3597-115">Этот атрибут может использоваться только один раз на параметр.</span><span class="sxs-lookup"><span data-stu-id="d3597-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="d3597-116">Можно использовать `Option` параметр атрибута, чтобы более детально определить шаблон.</span><span class="sxs-lookup"><span data-stu-id="d3597-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="d3597-117">Например можно сделать шаблон с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="d3597-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="d3597-118">Если этот атрибут применяется к коллекции, каждый элемент в коллекции должно соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="d3597-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="d3597-119">Атрибут ValidatePattern определяется [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="d3597-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3597-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d3597-120">See Also</span></span>

[<span data-ttu-id="d3597-121">System.Management.Automation.Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="d3597-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="d3597-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3597-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
