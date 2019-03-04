---
title: Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860440"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="f2dd1-102">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="f2dd1-103">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="f2dd1-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f2dd1-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для CustomItem представление (формат) Элемент для CustomEntry элемента ExpressionBinding представления (формат) для элемента CustomControlName CustomItem (формат) для привязки выражения для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2dd1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2dd1-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2dd1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f2dd1-107">Attributes and Elements</span></span>

<span data-ttu-id="f2dd1-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControlName` элемент.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2dd1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2dd1-109">Attributes</span></span>

<span data-ttu-id="f2dd1-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f2dd1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2dd1-111">Child Elements</span></span>

<span data-ttu-id="f2dd1-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2dd1-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f2dd1-113">Parent Elements</span></span>

|<span data-ttu-id="f2dd1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f2dd1-114">Element</span></span>|<span data-ttu-id="f2dd1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f2dd1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2dd1-116">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f2dd1-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f2dd1-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f2dd1-118">Text Value</span></span>

<span data-ttu-id="f2dd1-119">Укажите имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2dd1-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f2dd1-120">Remarks</span></span>

<span data-ttu-id="f2dd1-121">Можно создавать стандартные элементы управления, которые могут использоваться все представления файл форматирования, и можно создать элементы управления представления, которые могут использоваться по определенному представлению.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="f2dd1-122">Имена этих элементов управления задаются следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="f2dd1-123">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="f2dd1-124">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="f2dd1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f2dd1-125">See Also</span></span>

[<span data-ttu-id="f2dd1-126">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="f2dd1-127">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="f2dd1-128">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f2dd1-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2dd1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
