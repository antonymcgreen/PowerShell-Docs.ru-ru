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
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: f4bd4e116e22c8b5bfcb61680a7c42e58b4da93e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59983904"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="11f2d-102">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="11f2d-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="11f2d-103">Атрибут ValidateCount указывает минимальное и максимальное число аргументов для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="11f2d-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="11f2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11f2d-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="11f2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11f2d-105">Parameters</span></span>

<span data-ttu-id="11f2d-106">`MinLength` ([System.Int32][]) требуется.</span><span class="sxs-lookup"><span data-stu-id="11f2d-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="11f2d-107">Указывает минимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="11f2d-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="11f2d-108">`MaxLength`([System.Int32][]) требуется.</span><span class="sxs-lookup"><span data-stu-id="11f2d-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="11f2d-109">Указывает максимальное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="11f2d-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="11f2d-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="11f2d-110">Remarks</span></span>

- <span data-ttu-id="11f2d-111">Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [Как проверить количество аргументов][].</span><span class="sxs-lookup"><span data-stu-id="11f2d-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="11f2d-112">Если этот атрибут не вызывается, соответствующего параметра командлета может иметь любое количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="11f2d-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="11f2d-113">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="11f2d-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="11f2d-114">`MinLength` И `MaxLength` атрибут параметры не имеют тип [System.Int32][].</span><span class="sxs-lookup"><span data-stu-id="11f2d-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

    - <span data-ttu-id="11f2d-115">Значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.</span><span class="sxs-lookup"><span data-stu-id="11f2d-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="11f2d-116">Атрибут ValidateCount определяется [System.Management.Automation.ValidateCountAttribute][] класса.</span><span class="sxs-lookup"><span data-stu-id="11f2d-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="11f2d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="11f2d-117">See Also</span></span>

<span data-ttu-id="11f2d-118">[System.Management.Automation.ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="11f2d-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="11f2d-119">[Как проверить количество аргументов][]</span><span class="sxs-lookup"><span data-stu-id="11f2d-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="11f2d-120">[Запись командлета Windows PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="11f2d-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
