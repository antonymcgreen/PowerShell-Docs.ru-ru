---
title: Элемент DisplayError (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774292"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="36c6f-102">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="36c6f-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="36c6f-103">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="36c6f-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="36c6f-104">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="36c6f-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="36c6f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36c6f-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="36c6f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36c6f-106">Attributes and Elements</span></span>

<span data-ttu-id="36c6f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DisplayError` элемента.</span><span class="sxs-lookup"><span data-stu-id="36c6f-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="36c6f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36c6f-108">Attributes</span></span>

<span data-ttu-id="36c6f-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36c6f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="36c6f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36c6f-110">Child Elements</span></span>

<span data-ttu-id="36c6f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36c6f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36c6f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36c6f-112">Parent Elements</span></span>

|<span data-ttu-id="36c6f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="36c6f-113">Element</span></span>|<span data-ttu-id="36c6f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="36c6f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36c6f-115">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="36c6f-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="36c6f-116">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="36c6f-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="36c6f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="36c6f-117">Remarks</span></span>

<span data-ttu-id="36c6f-118">По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым.</span><span class="sxs-lookup"><span data-stu-id="36c6f-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="36c6f-119">Если этот элемент имеет значение true, будет отображена строка #ERR.</span><span class="sxs-lookup"><span data-stu-id="36c6f-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="36c6f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="36c6f-120">See Also</span></span>

[<span data-ttu-id="36c6f-121">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="36c6f-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="36c6f-122">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="36c6f-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
