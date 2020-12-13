---
ms.date: 09/13/2016
ms.topic: reference
title: Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета
description: Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659050"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="24f6a-103">Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="24f6a-103">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="24f6a-104">В этом разделе описывается добавление содержимого, которое отображается в разделах **Name** и **краткие** сведения справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="24f6a-104">This section describes how to add content that is displayed in the **NAME** and **SYNOPSIS** sections of the cmdlet help.</span></span> <span data-ttu-id="24f6a-105">В файле справки это содержимое добавляется в узел команды для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="24f6a-105">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="24f6a-106">Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24f6a-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="24f6a-107">Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24f6a-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="24f6a-108">Добавление имени командлета и кратких обзоров</span><span class="sxs-lookup"><span data-stu-id="24f6a-108">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="24f6a-109">Справка по командлету может отображать два описания для командлета.</span><span class="sxs-lookup"><span data-stu-id="24f6a-109">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="24f6a-110">Первое описание — это краткое описание, которое называется кратким.</span><span class="sxs-lookup"><span data-stu-id="24f6a-110">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="24f6a-111">Второе описание — более подробное описание, которое обсуждается в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="24f6a-111">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>
  <span data-ttu-id="24f6a-112">Оба эти описания должны быть написаны как один абзац.</span><span class="sxs-lookup"><span data-stu-id="24f6a-112">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="24f6a-113">В кратких обзорах имя командлета не повторяется.</span><span class="sxs-lookup"><span data-stu-id="24f6a-113">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="24f6a-114">Уведомление пользователя о том, что `Get-Server` командлет получает сервер, является кратким, но не информативным.</span><span class="sxs-lookup"><span data-stu-id="24f6a-114">Informing the user that the `Get-Server` cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="24f6a-115">Вместо этого используйте синонимы и добавьте подробные сведения в описание.</span><span class="sxs-lookup"><span data-stu-id="24f6a-115">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="24f6a-116">Пример: "получает объект, представляющий локальный или удаленный компьютер".</span><span class="sxs-lookup"><span data-stu-id="24f6a-116">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="24f6a-117">В кратком обзоре используйте простые команды, такие как "Get", "Create" и "Change".</span><span class="sxs-lookup"><span data-stu-id="24f6a-117">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="24f6a-118">Старайтесь не использовать "Set", поскольку он не является ясным, и обсловировать, например "Изменить".</span><span class="sxs-lookup"><span data-stu-id="24f6a-118">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="24f6a-119">Пример: "получение сведений о подписи Authenticode в файле".</span><span class="sxs-lookup"><span data-stu-id="24f6a-119">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="24f6a-120">Запись в Active Voice.</span><span class="sxs-lookup"><span data-stu-id="24f6a-120">Write in active voice.</span></span> <span data-ttu-id="24f6a-121">Например, "использовать объект TimeSpan..." намного более ясно, чем «объект TimeSpan может использоваться для...»</span><span class="sxs-lookup"><span data-stu-id="24f6a-121">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="24f6a-122">Избегайте команды "отобразить" при описании командлетов, получающих объекты.</span><span class="sxs-lookup"><span data-stu-id="24f6a-122">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="24f6a-123">Хотя Windows PowerShell отображает данные командлетов, важно рассказать пользователям о том, что командлет возвращает .NET Framework объекты, данные которых могут не отображаться.</span><span class="sxs-lookup"><span data-stu-id="24f6a-123">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="24f6a-124">Если выделить экран, пользователь может не знать, что командлет вернул много других полезных свойств и методов, которые не отображаются.</span><span class="sxs-lookup"><span data-stu-id="24f6a-124">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="24f6a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="24f6a-125">See Also</span></span>

[<span data-ttu-id="24f6a-126">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24f6a-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
