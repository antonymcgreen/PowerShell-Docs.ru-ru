---
title: Как добавить имя командлета и краткий обзор раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: f142548be473da15e702f4fa01835609d75b9d51
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861830"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="a36bb-102">Как добавить имя командлета и краткий обзор командлета в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="a36bb-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="a36bb-103">В этом разделе описывается добавление содержимого, которое отображается в разделах справки по командлетам имя и краткие сведения.</span><span class="sxs-lookup"><span data-stu-id="a36bb-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="a36bb-104">В файле справки это содержимое добавляется к узлу команду для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="a36bb-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a36bb-105">Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a36bb-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="a36bb-106">Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a36bb-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="a36bb-107">Чтобы добавить имя командлета и краткие сведения</span><span class="sxs-lookup"><span data-stu-id="a36bb-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="a36bb-108">Справка по командлетам можно отобразить два описания для командлета.</span><span class="sxs-lookup"><span data-stu-id="a36bb-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="a36bb-109">Первый приводится краткое описание, которое называется краткий обзор.</span><span class="sxs-lookup"><span data-stu-id="a36bb-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="a36bb-110">Второе описание является более подробное описание, которое рассматривается в [Добавление подробное описание для раздела справки командлета](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="a36bb-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="a36bb-111">Оба эти описания должно быть написано как один абзац.</span><span class="sxs-lookup"><span data-stu-id="a36bb-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="a36bb-112">Не повторять имя командлета в краткий обзор.</span><span class="sxs-lookup"><span data-stu-id="a36bb-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="a36bb-113">Где пользователю сообщается о том, что командлет Get-Server возвращает сервер краткий, но не информативные.</span><span class="sxs-lookup"><span data-stu-id="a36bb-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="a36bb-114">Вместо этого использовать синонимы и добавления сведений в описание.</span><span class="sxs-lookup"><span data-stu-id="a36bb-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="a36bb-115">Пример: «Получает объект, представляющий локальный или удаленный компьютер».</span><span class="sxs-lookup"><span data-stu-id="a36bb-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="a36bb-116">Используйте простой команды, например «get», «создать» и «изменить» в краткий обзор.</span><span class="sxs-lookup"><span data-stu-id="a36bb-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="a36bb-117">Старайтесь не использовать «set», поскольку он является неопределенным, и она же такие как «изменение.»</span><span class="sxs-lookup"><span data-stu-id="a36bb-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="a36bb-118">Пример: «Получает сведения о подписи Authenticode в файле».</span><span class="sxs-lookup"><span data-stu-id="a36bb-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="a36bb-119">Запись в действительном залоге.</span><span class="sxs-lookup"><span data-stu-id="a36bb-119">Write in active voice.</span></span> <span data-ttu-id="a36bb-120">Например «использовать объект TimeSpan...» намного более понятны, чем «определяется объектом TimeSpan может использоваться для...»</span><span class="sxs-lookup"><span data-stu-id="a36bb-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="a36bb-121">При описании командлетов, которые получают объекты, избегайте глагол «display».</span><span class="sxs-lookup"><span data-stu-id="a36bb-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="a36bb-122">Несмотря на то, что Windows PowerShell отображает данные командлета, очень важно для пользователей к понятию, командлет возвращает объекты .NET Framework, данные которых может не отображаться.</span><span class="sxs-lookup"><span data-stu-id="a36bb-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="a36bb-123">Если вы акцентировать внимание на отображение, пользователь можете не знать, что командлет может вернуть множество других полезных свойств и методов, которые не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a36bb-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a36bb-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a36bb-124">See Also</span></span>

 [<span data-ttu-id="a36bb-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a36bb-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)