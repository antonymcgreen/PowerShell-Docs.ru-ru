---
title: Объявление атрибута Валидатекаунт | Документация Майкрософт
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
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692378"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="c342b-102">Объявление атрибута ValidateCount</span><span class="sxs-lookup"><span data-stu-id="c342b-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="c342b-103">Атрибут Валидатекаунт указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="c342b-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="c342b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c342b-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="c342b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c342b-105">Parameters</span></span>

<span data-ttu-id="c342b-106">`MinLength`([System. Int32][]) обязательный.</span><span class="sxs-lookup"><span data-stu-id="c342b-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="c342b-107">Указывает минимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="c342b-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="c342b-108">`MaxLength`([System. Int32][]) обязательный.</span><span class="sxs-lookup"><span data-stu-id="c342b-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="c342b-109">Указывает максимальное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="c342b-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="c342b-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c342b-110">Remarks</span></span>

- <span data-ttu-id="c342b-111">Дополнительные сведения об объявлении этого атрибута см. в разделе [проверка числа аргументов][].</span><span class="sxs-lookup"><span data-stu-id="c342b-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="c342b-112">Если этот атрибут не вызывается, соответствующий параметр командлета может иметь любое количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="c342b-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="c342b-113">Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="c342b-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="c342b-114">`MinLength` `MaxLength` Параметры атрибута и не относятся к типу [System. Int32][].</span><span class="sxs-lookup"><span data-stu-id="c342b-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="c342b-115">Значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="c342b-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="c342b-116">Атрибут Валидатекаунт определяется классом [System. Management. Automation. валидатекаунтаттрибуте][] .</span><span class="sxs-lookup"><span data-stu-id="c342b-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c342b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c342b-117">See Also</span></span>

<span data-ttu-id="c342b-118">[System. Management. Automation. Валидатекаунтаттрибуте][]</span><span class="sxs-lookup"><span data-stu-id="c342b-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="c342b-119">[Как проверить количество аргументов][]</span><span class="sxs-lookup"><span data-stu-id="c342b-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="c342b-120">[Запись командлета Windows PowerShell][]</span><span class="sxs-lookup"><span data-stu-id="c342b-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. Валидатекаунтаттрибуте]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
