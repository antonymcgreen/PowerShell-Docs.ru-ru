---
title: Объявление атрибута OutputType | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365343"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="246be-102">Объявление атрибута для типа выходных данных</span><span class="sxs-lookup"><span data-stu-id="246be-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="246be-103">Атрибут `OutputType` определяет типы .NET Framework, возвращаемые командлетом, функцией или скриптом.</span><span class="sxs-lookup"><span data-stu-id="246be-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="246be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="246be-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="246be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="246be-105">Parameters</span></span>

<span data-ttu-id="246be-106">Требуется тип (`string[]` или `Type[]`).</span><span class="sxs-lookup"><span data-stu-id="246be-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="246be-107">Указывает типы, возвращаемые функцией командлета или скриптом.</span><span class="sxs-lookup"><span data-stu-id="246be-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="246be-108">Параметерсетнаме (String []) необязательный.</span><span class="sxs-lookup"><span data-stu-id="246be-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="246be-109">Задает наборы параметров, которые возвращают типы, указанные в параметре `type`.</span><span class="sxs-lookup"><span data-stu-id="246be-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="246be-110">Провидеркмдлет необязательный.</span><span class="sxs-lookup"><span data-stu-id="246be-110">providerCmdlet Optional.</span></span> <span data-ttu-id="246be-111">Указывает командлет поставщика, возвращающий типы, указанные в параметре `type`.</span><span class="sxs-lookup"><span data-stu-id="246be-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="246be-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="246be-112">See Also</span></span>

[<span data-ttu-id="246be-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="246be-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
