---
title: Объявление атрибута ValidateCount | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: 1a7b5ea340fe5212d003c97a9017278d6c631355
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859160"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="68768-102">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="68768-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="68768-103">Атрибут ValidateCount указывает минимальное и максимальное число аргументов для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="68768-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="68768-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68768-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="68768-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68768-105">Parameters</span></span>

<span data-ttu-id="68768-106">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) требуется.</span><span class="sxs-lookup"><span data-stu-id="68768-106">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="68768-107">Указывает минимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="68768-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="68768-108">`MaxLength`([System.Int32](/dotnet/api/System.Int32)) требуется.</span><span class="sxs-lookup"><span data-stu-id="68768-108">`MaxLength`([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="68768-109">Указывает максимальное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="68768-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="68768-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="68768-110">Remarks</span></span>

- <span data-ttu-id="68768-111">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span><span class="sxs-lookup"><span data-stu-id="68768-111">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span></span>

- <span data-ttu-id="68768-112">Если этот атрибут не вызывается, соответствующего параметра командлета может иметь любое количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="68768-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="68768-113">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="68768-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="68768-114">`MinLength` И `MaxLength` атрибут параметры не имеют тип [System.Int32](/dotnet/api/System.Int32).</span><span class="sxs-lookup"><span data-stu-id="68768-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32](/dotnet/api/System.Int32).</span></span>

    - <span data-ttu-id="68768-115">Значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="68768-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="68768-116">Атрибут ValidateCount определяется [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount) класса.</span><span class="sxs-lookup"><span data-stu-id="68768-116">The ValidateCount attribute is defined by the [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="68768-117">См. также</span><span class="sxs-lookup"><span data-stu-id="68768-117">See Also</span></span>

[<span data-ttu-id="68768-118">System.Management.Automation.Validatecount</span><span class="sxs-lookup"><span data-stu-id="68768-118">System.Management.Automation.Validatecount</span></span>](/dotnet/api/System.Management.Automation.ValidateCount)

[<span data-ttu-id="68768-119">Как объявить правила проверки входных данных</span><span class="sxs-lookup"><span data-stu-id="68768-119">How to Declare Input Validation Rules</span></span>](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[<span data-ttu-id="68768-120">Как объявить правила проверки входных данных</span><span class="sxs-lookup"><span data-stu-id="68768-120">How to Declare Input Validation Rules</span></span>](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[<span data-ttu-id="68768-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68768-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
