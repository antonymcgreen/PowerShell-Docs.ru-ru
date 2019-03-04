---
title: Объявление атрибута псевдоним | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.assetid: d0df3a46-b1cc-42b9-beb1-e16bce254007
caps.latest.revision: 10
ms.openlocfilehash: 4d20672c5181c994c1b53624f6c42a301db11f26
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855050"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="467e2-102">Объявление атрибута псевдонима</span><span class="sxs-lookup"><span data-stu-id="467e2-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="467e2-103">Alias-атрибут позволяет пользователю указать другие имена для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="467e2-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="467e2-104">Псевдонимы могут использоваться для предоставления ярлыков для имени параметра, или они могут предоставлять разные имена, которые подходят для разных сценариев.</span><span class="sxs-lookup"><span data-stu-id="467e2-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="467e2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="467e2-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="467e2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="467e2-106">Parameters</span></span>

<span data-ttu-id="467e2-107">`aliasName` (String[]) Обязательно.</span><span class="sxs-lookup"><span data-stu-id="467e2-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="467e2-108">Задает набор имен с разделителями запятыми псевдоним для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="467e2-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="467e2-109">Замечания</span><span class="sxs-lookup"><span data-stu-id="467e2-109">Remarks</span></span>

- <span data-ttu-id="467e2-110">Alias-атрибут используется с атрибутом параметр, при указании параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="467e2-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="467e2-111">Дополнительные сведения о том, как объявить этих атрибутов см. в разделе [как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="467e2-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="467e2-112">Каждое имя псевдонима должно быть уникальным в пределах командлета.</span><span class="sxs-lookup"><span data-stu-id="467e2-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="467e2-113">Windows PowerShell не проверяет наличие повторяющихся псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="467e2-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="467e2-114">Alias-атрибут используется один раз для каждого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="467e2-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="467e2-115">Alias-атрибут определяется [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="467e2-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="467e2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="467e2-116">See Also</span></span>

[<span data-ttu-id="467e2-117">Псевдонимы параметра</span><span class="sxs-lookup"><span data-stu-id="467e2-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="467e2-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="467e2-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
