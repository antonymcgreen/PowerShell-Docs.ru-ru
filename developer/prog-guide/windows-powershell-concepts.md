---
title: Основные понятия Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3dd5608e-50b6-4c6a-aee3-dde0e86032bc
caps.latest.revision: 7
ms.openlocfilehash: c4b13518ad6452a39ca49e897e1d3e353818d332
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860760"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="fad2c-102">Основные понятия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="fad2c-103">Этот раздел содержит общие сведения, которые помогут вам понять Windows PowerShell с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="fad2c-103">This section contains conceptual information that will help you understand Windows PowerShell from the viewpoint of a developer.</span></span>

|<span data-ttu-id="fad2c-104">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="fad2c-104">Topic Name</span></span>|<span data-ttu-id="fad2c-105">Описание</span><span class="sxs-lookup"><span data-stu-id="fad2c-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="fad2c-106">Поставщики Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-106">Windows PowerShell Providers</span></span>](http://msdn.microsoft.com/en-us/a65c5c75-1131-4ade-90d3-a613dbe620e9)|<span data-ttu-id="fad2c-107">Содержит обсуждение о поставщиках Windows PowerShell, которые используются для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="fad2c-107">A discussion about Windows PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="fad2c-108">Оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-108">Windows PowerShell Snap-ins</span></span>](http://msdn.microsoft.com/en-us/20e081a9-522c-48bf-9f21-faaf8cca2e82)|<span data-ttu-id="fad2c-109">Механизм для регистрации командлетов и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="fad2c-109">A mechanism for registering cmdlets and providers.</span></span> <span data-ttu-id="fad2c-110">(См. также [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).)</span><span class="sxs-lookup"><span data-stu-id="fad2c-110">(See also, [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).)</span></span>|
|[<span data-ttu-id="fad2c-111">Среда выполнения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-111">Windows PowerShell Runtime</span></span>](http://msdn.microsoft.com/en-us/949f06e8-0224-4cd3-bbad-a0cebbb5dec8)|<span data-ttu-id="fad2c-112">Текущий экземпляр пространства выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fad2c-112">The current instance of the Windows PowerShell runspace.</span></span>|
|[<span data-ttu-id="fad2c-113">Пространства выполнения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-113">Windows PowerShell Runspaces</span></span>](http://msdn.microsoft.com/en-us/a1582cfe-f06d-4aff-adc6-71f49a860ce9)|<span data-ttu-id="fad2c-114">Рабочие среды, где команды обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="fad2c-114">The operating environments where commands are processed.</span></span>|
|[<span data-ttu-id="fad2c-115">Пространства имен Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-115">Windows PowerShell Namespaces</span></span>](http://msdn.microsoft.com/en-us/04bd2841-e90c-47d2-8a1f-3aeb3df35176)|<span data-ttu-id="fad2c-116">Общие сведения о пространствах имен Windows PowerShell API.</span><span class="sxs-lookup"><span data-stu-id="fad2c-116">Overview of Windows PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="fad2c-117">Справка Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-117">Windows PowerShell Help</span></span>](http://msdn.microsoft.com/en-us/097b7c1c-a056-4b36-9c86-65b2ee702fc7)|<span data-ttu-id="fad2c-118">Обсуждение о создании справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="fad2c-118">A discussion about writing cmdlet Help.</span></span>|
|[<span data-ttu-id="fad2c-119">Запрос на подтверждение</span><span class="sxs-lookup"><span data-stu-id="fad2c-119">Requesting Confirmation</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="fad2c-120">Берется рассказ о том, как командлеты и поставщики запрос на отзыв от пользователя перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="fad2c-120">A discussion about how cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="fad2c-121">Основные понятия Windows PowerShell объекта</span><span class="sxs-lookup"><span data-stu-id="fad2c-121">Windows PowerShell Object Concepts</span></span>](http://msdn.microsoft.com/en-us/a1449178-b6fd-4ca8-a5e1-d747c2c54181)|<span data-ttu-id="fad2c-122">Как Windows PowerShell обрабатывает объекты.</span><span class="sxs-lookup"><span data-stu-id="fad2c-122">How Windows PowerShell handles objects.</span></span>|
|[<span data-ttu-id="fad2c-123">Windows PowerShell расширенной системы типов (ETS)</span><span class="sxs-lookup"><span data-stu-id="fad2c-123">Windows PowerShell Extended Type System (ETS)</span></span>](http://msdn.microsoft.com/en-us/12700631-be23-4e6b-9bf0-81ea0d166353)|<span data-ttu-id="fad2c-124">Программное расширение объектов.</span><span class="sxs-lookup"><span data-stu-id="fad2c-124">Programmatically extending objects.</span></span>|

## <a name="see-also"></a><span data-ttu-id="fad2c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fad2c-125">See Also</span></span>

[<span data-ttu-id="fad2c-126">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad2c-126">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)