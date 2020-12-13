---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута псевдонима
description: Объявление атрибута псевдонима
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668309"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="36710-103">Объявление атрибута псевдонима</span><span class="sxs-lookup"><span data-stu-id="36710-103">Alias Attribute Declaration</span></span>

<span data-ttu-id="36710-104">Атрибут Alias позволяет пользователю указать различные имена для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="36710-104">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="36710-105">Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="36710-105">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="36710-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36710-106">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="36710-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="36710-107">Parameters</span></span>

<span data-ttu-id="36710-108">`aliasName` (String []) Обязательно.</span><span class="sxs-lookup"><span data-stu-id="36710-108">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="36710-109">Задает набор разделенных запятыми имен псевдонимов для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="36710-109">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="36710-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="36710-110">Remarks</span></span>

- <span data-ttu-id="36710-111">Атрибут Alias используется с атрибутом Parameter при указании параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="36710-111">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="36710-112">Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="36710-112">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="36710-113">Каждое имя псевдонима должно быть уникальным в пределах командлета.</span><span class="sxs-lookup"><span data-stu-id="36710-113">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="36710-114">Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="36710-114">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="36710-115">Атрибут Alias используется один раз для каждого параметра в командлете.</span><span class="sxs-lookup"><span data-stu-id="36710-115">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="36710-116">Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .</span><span class="sxs-lookup"><span data-stu-id="36710-116">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="36710-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="36710-117">See Also</span></span>

[<span data-ttu-id="36710-118">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="36710-118">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="36710-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36710-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
