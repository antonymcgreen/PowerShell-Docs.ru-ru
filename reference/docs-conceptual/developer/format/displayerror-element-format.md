---
title: Элемент DisplayError (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363993"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="6a178-102">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="6a178-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="6a178-103">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="6a178-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="6a178-104">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="6a178-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6a178-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a178-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6a178-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6a178-106">Attributes and Elements</span></span>

<span data-ttu-id="6a178-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `DisplayError`.</span><span class="sxs-lookup"><span data-stu-id="6a178-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a178-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a178-108">Attributes</span></span>

<span data-ttu-id="6a178-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="6a178-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6a178-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a178-110">Child Elements</span></span>

<span data-ttu-id="6a178-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="6a178-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6a178-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a178-112">Parent Elements</span></span>

|<span data-ttu-id="6a178-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a178-113">Element</span></span>|<span data-ttu-id="6a178-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6a178-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a178-115">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="6a178-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="6a178-116">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6a178-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6a178-117">Замечания</span><span class="sxs-lookup"><span data-stu-id="6a178-117">Remarks</span></span>

<span data-ttu-id="6a178-118">По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым.</span><span class="sxs-lookup"><span data-stu-id="6a178-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="6a178-119">Если этот элемент имеет значение true, будет отображена строка #ERR.</span><span class="sxs-lookup"><span data-stu-id="6a178-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a178-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a178-120">See Also</span></span>

[<span data-ttu-id="6a178-121">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="6a178-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="6a178-122">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a178-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
