---
title: TypeName-элемент для SelectionCondition для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477c8711-fffc-4f92-af45-6d4f80990474
caps.latest.revision: 7
ms.openlocfilehash: 60f02f3240c5574e1b1f9027b060bd9af89a11d2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853600"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="c9c9a-102">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="c9c9a-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c9c9a-103">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="c9c9a-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c9c9a-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для элементов управления для Элемент конфигурации (формат) CustomEntry для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента конфигурации (формат) SelectionCondition для EntrySelectedBy для CustomEntry для Элемент конфигурации (формат) TypeName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="c9c9a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c9c9a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9c9a-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c9c9a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9c9a-107">Attributes and Elements</span></span>

<span data-ttu-id="c9c9a-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c9c9a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9c9a-109">Attributes</span></span>

<span data-ttu-id="c9c9a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c9c9a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9c9a-111">Child Elements</span></span>

<span data-ttu-id="c9c9a-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c9c9a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9c9a-113">Parent Elements</span></span>

|<span data-ttu-id="c9c9a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9c9a-114">Element</span></span>|<span data-ttu-id="c9c9a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c9c9a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c9c9a-116">Элемент SelectionCondition для EntrySelectedBy для CustomEntry для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="c9c9a-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c9c9a-117">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c9c9a-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c9c9a-118">Text Value</span></span>

<span data-ttu-id="c9c9a-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="c9c9a-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9c9a-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="c9c9a-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="c9c9a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c9c9a-121">See Also</span></span>

[<span data-ttu-id="c9c9a-122">Элемент SelectionCondition для EntrySelectedBy для CustomEntry для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="c9c9a-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="c9c9a-123">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9c9a-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
