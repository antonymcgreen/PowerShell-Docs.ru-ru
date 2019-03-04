---
title: Элемент DisplayError (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 431e5d8407b9f689a5224b329d8c7b52802e19e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854920"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="696a2-102">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="696a2-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="696a2-103">Указывает, что строка #ERR отображаются при возникновении ошибки, отображение фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="696a2-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="696a2-104">DisplayError элемент DefaultSettings (формат) элемент (Frmat) для конфигурации элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="696a2-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Frmat)</span></span>

## <a name="syntax"></a><span data-ttu-id="696a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="696a2-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="696a2-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="696a2-106">Attributes and Elements</span></span>

<span data-ttu-id="696a2-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `DisplayError` элемент.</span><span class="sxs-lookup"><span data-stu-id="696a2-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="696a2-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="696a2-108">Attributes</span></span>

<span data-ttu-id="696a2-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="696a2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="696a2-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="696a2-110">Child Elements</span></span>

<span data-ttu-id="696a2-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="696a2-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="696a2-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="696a2-112">Parent Elements</span></span>

|<span data-ttu-id="696a2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="696a2-113">Element</span></span>|<span data-ttu-id="696a2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="696a2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="696a2-115">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="696a2-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="696a2-116">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="696a2-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="696a2-117">Замечания</span><span class="sxs-lookup"><span data-stu-id="696a2-117">Remarks</span></span>

<span data-ttu-id="696a2-118">По умолчанию при возникновении ошибки при попытке отображения фрагмента данных, расположение данных будет пустым.</span><span class="sxs-lookup"><span data-stu-id="696a2-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="696a2-119">Когда этот элемент имеет значение true, то строка #ERR будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="696a2-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="696a2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="696a2-120">See Also</span></span>

[<span data-ttu-id="696a2-121">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="696a2-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="696a2-122">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="696a2-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
