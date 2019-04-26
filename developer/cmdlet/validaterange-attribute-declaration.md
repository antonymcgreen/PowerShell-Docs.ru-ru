---
title: Объявление атрибута ValidateRange | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067116"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="de5d1-102">Объявление атрибута ValidateRange</span><span class="sxs-lookup"><span data-stu-id="de5d1-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="de5d1-103">Атрибут ValidateRange указывает минимальное и максимальное значения (диапазона) для аргумента параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="de5d1-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="de5d1-104">Этот атрибут также может использоваться функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de5d1-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="de5d1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de5d1-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="de5d1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="de5d1-106">Parameters</span></span>

<span data-ttu-id="de5d1-107">`MinRange` ([System.Object](/dotnet/api/system.object)) требуется.</span><span class="sxs-lookup"><span data-stu-id="de5d1-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="de5d1-108">Задает минимальное допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="de5d1-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="de5d1-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) требуется.</span><span class="sxs-lookup"><span data-stu-id="de5d1-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="de5d1-110">Указывает максимально допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="de5d1-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="de5d1-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="de5d1-111">Remarks</span></span>

- <span data-ttu-id="de5d1-112">Среда выполнения Windows PowerShell создает ошибку построения при значение `MinRange` параметр больше, чем значение `MaxRange` параметра.</span><span class="sxs-lookup"><span data-stu-id="de5d1-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="de5d1-113">Среда выполнения Windows PowerShell создает ошибку проверки при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="de5d1-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="de5d1-114">Если значение аргумента равно меньше, чем `MinRange` ограничение или больше, чем `MaxRange` ограничение.</span><span class="sxs-lookup"><span data-stu-id="de5d1-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="de5d1-115">Когда аргумент не имеет тот же тип, что `MinRange` и `MaxRange` параметров.</span><span class="sxs-lookup"><span data-stu-id="de5d1-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="de5d1-116">Атрибут ValidateRange определяется [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="de5d1-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="de5d1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="de5d1-117">See Also</span></span>

[<span data-ttu-id="de5d1-118">System.Management.Automation.Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="de5d1-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="de5d1-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de5d1-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
