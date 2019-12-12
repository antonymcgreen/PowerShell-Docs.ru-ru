---
title: Объявление атрибута Alias | Документация Майкрософт
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72370023"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="30684-102">Объявление атрибута псевдонима</span><span class="sxs-lookup"><span data-stu-id="30684-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="30684-103">Атрибут Alias позволяет пользователю указать различные имена для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="30684-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="30684-104">Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="30684-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="30684-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30684-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="30684-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="30684-106">Parameters</span></span>

<span data-ttu-id="30684-107">Требуется `aliasName` (String []).</span><span class="sxs-lookup"><span data-stu-id="30684-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="30684-108">Задает набор разделенных запятыми имен псевдонимов для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="30684-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="30684-109">Замечания</span><span class="sxs-lookup"><span data-stu-id="30684-109">Remarks</span></span>

- <span data-ttu-id="30684-110">Атрибут Alias используется с атрибутом Parameter при указании параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="30684-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="30684-111">Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="30684-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="30684-112">Каждое имя псевдонима должно быть уникальным в пределах командлета.</span><span class="sxs-lookup"><span data-stu-id="30684-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="30684-113">Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="30684-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="30684-114">Атрибут Alias используется один раз для каждого параметра в командлете.</span><span class="sxs-lookup"><span data-stu-id="30684-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="30684-115">Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .</span><span class="sxs-lookup"><span data-stu-id="30684-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="30684-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="30684-116">See Also</span></span>

[<span data-ttu-id="30684-117">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="30684-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="30684-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30684-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
