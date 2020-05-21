---
title: Добавление имени командлета и кратких сведений в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: 5b4c04a14c3d86c7a3b94b768e8fb59116d8c6f5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560633"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="571ba-102">Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="571ba-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="571ba-103">В этом разделе описывается добавление содержимого, которое отображается в разделах NAME и КРАТКИе сведения справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="571ba-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="571ba-104">В файле справки это содержимое добавляется в узел команды для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="571ba-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="571ba-105">Для получения полного представления файла справки откройте один из файлов длл-Хелп. XML, расположенный в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="571ba-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="571ba-106">Например, файл Microsoft. PowerShell. Commands. Management. длл-Хелп. XML содержит содержимое для некоторых командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="571ba-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="571ba-107">Добавление имени командлета и кратких обзоров</span><span class="sxs-lookup"><span data-stu-id="571ba-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="571ba-108">Справка по командлету может отображать два описания для командлета.</span><span class="sxs-lookup"><span data-stu-id="571ba-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="571ba-109">Первое описание — это краткое описание, которое называется кратким.</span><span class="sxs-lookup"><span data-stu-id="571ba-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="571ba-110">Второе описание — более подробное описание, которое обсуждается в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="571ba-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="571ba-111">Оба эти описания должны быть написаны как один абзац.</span><span class="sxs-lookup"><span data-stu-id="571ba-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="571ba-112">В кратких обзорах имя командлета не повторяется.</span><span class="sxs-lookup"><span data-stu-id="571ba-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="571ba-113">Уведомление пользователя о том, что командлет Get-Server получает сервер, краткий, но не информативный.</span><span class="sxs-lookup"><span data-stu-id="571ba-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="571ba-114">Вместо этого используйте синонимы и добавьте подробные сведения в описание.</span><span class="sxs-lookup"><span data-stu-id="571ba-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="571ba-115">Пример: "получает объект, представляющий локальный или удаленный компьютер".</span><span class="sxs-lookup"><span data-stu-id="571ba-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="571ba-116">В кратком обзоре используйте простые команды, такие как "Get", "Create" и "Change".</span><span class="sxs-lookup"><span data-stu-id="571ba-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="571ba-117">Старайтесь не использовать "Set", поскольку он не является ясным, и обсловировать, например "Изменить".</span><span class="sxs-lookup"><span data-stu-id="571ba-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="571ba-118">Пример: "получение сведений о подписи Authenticode в файле".</span><span class="sxs-lookup"><span data-stu-id="571ba-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="571ba-119">Запись в Active Voice.</span><span class="sxs-lookup"><span data-stu-id="571ba-119">Write in active voice.</span></span> <span data-ttu-id="571ba-120">Например, "использовать объект TimeSpan..." намного более ясно, чем «объект TimeSpan может использоваться для...»</span><span class="sxs-lookup"><span data-stu-id="571ba-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="571ba-121">Избегайте команды "отобразить" при описании командлетов, получающих объекты.</span><span class="sxs-lookup"><span data-stu-id="571ba-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="571ba-122">Хотя Windows PowerShell отображает данные командлетов, важно рассказать пользователям о том, что командлет возвращает .NET Framework объекты, данные которых могут не отображаться.</span><span class="sxs-lookup"><span data-stu-id="571ba-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="571ba-123">Если выделить экран, пользователь может не знать, что командлет вернул много других полезных свойств и методов, которые не отображаются.</span><span class="sxs-lookup"><span data-stu-id="571ba-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="571ba-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="571ba-124">See Also</span></span>

 [<span data-ttu-id="571ba-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="571ba-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
