---
ms.date: 09/13/2016
ms.topic: reference
title: Как добавить описание командлета
description: Как добавить описание командлета
ms.openlocfilehash: 08d21a281881678423bbe3c382279875ed2868db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651211"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="8208c-103">Как добавить описание командлета</span><span class="sxs-lookup"><span data-stu-id="8208c-103">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="8208c-104">В этом разделе описывается добавление содержимого, которое отображается в разделе **Описание** справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="8208c-104">This section describes how to add content that is displayed in the **DESCRIPTION** section of the cmdlet Help.</span></span> <span data-ttu-id="8208c-105">В файле справки это содержимое добавляется в узел **команды** для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="8208c-105">In the Help file, this content is added to the **Command** node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8208c-106">Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8208c-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="8208c-107">Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8208c-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="8208c-108">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="8208c-108">To Add a Description</span></span>

- <span data-ttu-id="8208c-109">Начните с объяснения основных функций командлета более подробно.</span><span class="sxs-lookup"><span data-stu-id="8208c-109">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="8208c-110">Во многих случаях можно объяснить термины, используемые в имени командлета, и проиллюстрировать неизвестные концепции с помощью примера.</span><span class="sxs-lookup"><span data-stu-id="8208c-110">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="8208c-111">Например, если командлет добавляет данные в файл, объясните, что он добавляет данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="8208c-111">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="8208c-112">Чтобы найти все функции командлета, ознакомьтесь со списком параметров.</span><span class="sxs-lookup"><span data-stu-id="8208c-112">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="8208c-113">Опишите основную функцию командлета, а затем включите другие функции и функции.</span><span class="sxs-lookup"><span data-stu-id="8208c-113">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="8208c-114">Например, если основной функцией командлета является изменение одного свойства, но командлет может изменить все свойства, скажем, в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="8208c-114">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="8208c-115">Если параметры командлета позволяют пользователям запросить информацию различными способами, объясните их.</span><span class="sxs-lookup"><span data-stu-id="8208c-115">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="8208c-116">Включите сведения о способах, с помощью которых пользователи могут использовать командлет, в дополнение к очевидным применениям.</span><span class="sxs-lookup"><span data-stu-id="8208c-116">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="8208c-117">Например, можно использовать объект, который `Get-Host` извлекает командлет, для изменения цвета текста в командном окне Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8208c-117">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="8208c-118">Пример: " `Get-Acl` командлет получает объекты, представляющие дескриптор безопасности файла или ресурса.</span><span class="sxs-lookup"><span data-stu-id="8208c-118">Example: "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="8208c-119">Дескриптор безопасности содержит списки управления доступом (ACL) ресурса.</span><span class="sxs-lookup"><span data-stu-id="8208c-119">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="8208c-120">Список ACL задает разрешения, которые пользователи и группы пользователей должны иметь к ресурсу. "</span><span class="sxs-lookup"><span data-stu-id="8208c-120">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="8208c-121">Подробное описание должно описывать командлет, но не должно описывать концепции, используемые командлетом.</span><span class="sxs-lookup"><span data-stu-id="8208c-121">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="8208c-122">Помещайте определения концепций в дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="8208c-122">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="8208c-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="8208c-123">See Also</span></span>

[<span data-ttu-id="8208c-124">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8208c-124">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
