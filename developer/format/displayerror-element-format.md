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
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056487"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="38ae6-102">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="38ae6-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="38ae6-103">Указывает, что строка #ERR отображаются при возникновении ошибки, отображение фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="38ae6-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="38ae6-104">DisplayError элемент DefaultSettings (формат) элемент (формат) для конфигурации элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="38ae6-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="38ae6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38ae6-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="38ae6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38ae6-106">Attributes and Elements</span></span>

<span data-ttu-id="38ae6-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `DisplayError` элемент.</span><span class="sxs-lookup"><span data-stu-id="38ae6-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="38ae6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38ae6-108">Attributes</span></span>

<span data-ttu-id="38ae6-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="38ae6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="38ae6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38ae6-110">Child Elements</span></span>

<span data-ttu-id="38ae6-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="38ae6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="38ae6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38ae6-112">Parent Elements</span></span>

|<span data-ttu-id="38ae6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="38ae6-113">Element</span></span>|<span data-ttu-id="38ae6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="38ae6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38ae6-115">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="38ae6-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="38ae6-116">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="38ae6-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="38ae6-117">Замечания</span><span class="sxs-lookup"><span data-stu-id="38ae6-117">Remarks</span></span>

<span data-ttu-id="38ae6-118">По умолчанию при возникновении ошибки при попытке отображения фрагмента данных, расположение данных будет пустым.</span><span class="sxs-lookup"><span data-stu-id="38ae6-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="38ae6-119">Когда этот элемент имеет значение true, то строка #ERR будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="38ae6-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="38ae6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="38ae6-120">See Also</span></span>

[<span data-ttu-id="38ae6-121">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="38ae6-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="38ae6-122">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="38ae6-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
