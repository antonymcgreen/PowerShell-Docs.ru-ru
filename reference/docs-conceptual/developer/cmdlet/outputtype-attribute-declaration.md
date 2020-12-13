---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута для типа выходных данных
description: Объявление атрибута для типа выходных данных
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646466"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="92d70-103">Объявление атрибута для типа выходных данных</span><span class="sxs-lookup"><span data-stu-id="92d70-103">OutputType Attribute Declaration</span></span>

<span data-ttu-id="92d70-104">`OutputType`Атрибут определяет типы .NET Framework, возвращаемые командлетом, функцией или скриптом.</span><span class="sxs-lookup"><span data-stu-id="92d70-104">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="92d70-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92d70-105">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="92d70-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="92d70-106">Parameters</span></span>

<span data-ttu-id="92d70-107">`string[]`Обязательный тип (или `Type[]` ).</span><span class="sxs-lookup"><span data-stu-id="92d70-107">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="92d70-108">Указывает типы, возвращаемые функцией командлета или скриптом.</span><span class="sxs-lookup"><span data-stu-id="92d70-108">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="92d70-109">Параметерсетнаме (String []) необязательный.</span><span class="sxs-lookup"><span data-stu-id="92d70-109">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="92d70-110">Задает наборы параметров, которые возвращают типы, указанные в `type` параметре.</span><span class="sxs-lookup"><span data-stu-id="92d70-110">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="92d70-111">Провидеркмдлет необязательный.</span><span class="sxs-lookup"><span data-stu-id="92d70-111">providerCmdlet Optional.</span></span> <span data-ttu-id="92d70-112">Указывает командлет поставщика, возвращающий типы, указанные в `type` параметре.</span><span class="sxs-lookup"><span data-stu-id="92d70-112">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="92d70-113">См. также</span><span class="sxs-lookup"><span data-stu-id="92d70-113">See Also</span></span>

[<span data-ttu-id="92d70-114">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92d70-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
