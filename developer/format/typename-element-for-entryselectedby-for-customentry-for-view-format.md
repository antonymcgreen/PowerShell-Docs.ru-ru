---
title: TypeName-элемент для EntrySelectedBy для CustomEntry для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083983"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="2dd0a-102">Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="2dd0a-103">Указывает тип .NET, который использует это определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="2dd0a-104">Нет ограничений на число типов, которые могут быть указаны для определения.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="2dd0a-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для элемента представления (формат) TypeName для EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2dd0a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dd0a-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2dd0a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2dd0a-107">Attributes and Elements</span></span>

<span data-ttu-id="2dd0a-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2dd0a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2dd0a-109">Attributes</span></span>

<span data-ttu-id="2dd0a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2dd0a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2dd0a-111">Child Elements</span></span>

<span data-ttu-id="2dd0a-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2dd0a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2dd0a-113">Parent Elements</span></span>

|<span data-ttu-id="2dd0a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2dd0a-114">Element</span></span>|<span data-ttu-id="2dd0a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2dd0a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2dd0a-116">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="2dd0a-117">Определяет типы .NET, использующих это определение представления пользовательского элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2dd0a-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2dd0a-118">Text Value</span></span>

<span data-ttu-id="2dd0a-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dd0a-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="2dd0a-120">Remarks</span></span>

<span data-ttu-id="2dd0a-121">Каждое определение представления пользовательского элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2dd0a-122">Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2dd0a-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2dd0a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2dd0a-123">See Also</span></span>

[<span data-ttu-id="2dd0a-124">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="2dd0a-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2dd0a-125">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2dd0a-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dd0a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
