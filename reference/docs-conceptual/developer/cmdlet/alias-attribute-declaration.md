---
title: Объявление атрибута Alias | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782418"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="9c300-102">Объявление атрибута псевдонима</span><span class="sxs-lookup"><span data-stu-id="9c300-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="9c300-103">Атрибут Alias позволяет пользователю указать различные имена для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="9c300-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="9c300-104">Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="9c300-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c300-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c300-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="9c300-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c300-106">Parameters</span></span>

<span data-ttu-id="9c300-107">`aliasName`(String []) Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9c300-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="9c300-108">Задает набор разделенных запятыми имен псевдонимов для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="9c300-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c300-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c300-109">Remarks</span></span>

- <span data-ttu-id="9c300-110">Атрибут Alias используется с атрибутом Parameter при указании параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="9c300-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="9c300-111">Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9c300-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="9c300-112">Каждое имя псевдонима должно быть уникальным в пределах командлета.</span><span class="sxs-lookup"><span data-stu-id="9c300-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="9c300-113">Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="9c300-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="9c300-114">Атрибут Alias используется один раз для каждого параметра в командлете.</span><span class="sxs-lookup"><span data-stu-id="9c300-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="9c300-115">Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .</span><span class="sxs-lookup"><span data-stu-id="9c300-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c300-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9c300-116">See Also</span></span>

[<span data-ttu-id="9c300-117">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="9c300-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="9c300-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c300-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
