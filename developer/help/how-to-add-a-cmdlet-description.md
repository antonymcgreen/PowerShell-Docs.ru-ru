---
title: Как добавить описание командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862600"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="3284a-102">Как добавить описание командлета</span><span class="sxs-lookup"><span data-stu-id="3284a-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="3284a-103">В этом разделе описывается добавление содержимого, которое отображается в разделе "Описание" справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="3284a-103">This section describes how to add content that is displayed in the DESCRIPTION section of the cmdlet Help.</span></span> <span data-ttu-id="3284a-104">В файле справки это содержимое добавляется к узлу команду для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="3284a-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3284a-105">Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3284a-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="3284a-106">Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3284a-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="3284a-107">Чтобы добавить описание</span><span class="sxs-lookup"><span data-stu-id="3284a-107">To Add a Description</span></span>

- <span data-ttu-id="3284a-108">Начните с объяснением основные функции этого командлета, более подробно.</span><span class="sxs-lookup"><span data-stu-id="3284a-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="3284a-109">Во многих случаях можно объяснить терминов, используемых в имени командлета и иллюстрируют понятия не знакомы с примером.</span><span class="sxs-lookup"><span data-stu-id="3284a-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="3284a-110">Например если командлет добавляет данные в файл, объясните, что он добавляет данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="3284a-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="3284a-111">Чтобы найти все функции командлета, просмотрите список параметров.</span><span class="sxs-lookup"><span data-stu-id="3284a-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="3284a-112">Описания основная функция командлета и включите другие функции и возможности.</span><span class="sxs-lookup"><span data-stu-id="3284a-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="3284a-113">Если основная функция командлет является изменение одного свойства, но командлет можно изменить все свойства, например, в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="3284a-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="3284a-114">Если параметры командлета позволяют запросить сведения по-разному, объяснения этого.</span><span class="sxs-lookup"><span data-stu-id="3284a-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="3284a-115">Включить сведения о том, что пользователи могут использовать командлет, помимо очевидных использует.</span><span class="sxs-lookup"><span data-stu-id="3284a-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="3284a-116">Например, можно использовать объект, `Get-Host` командлет извлекает изменение цвета текста в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3284a-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="3284a-117">Пример:  « `Get-Acl` Командлет возвращает объекты, представляющие дескриптор безопасности файла или ресурса.</span><span class="sxs-lookup"><span data-stu-id="3284a-117">Example:  "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="3284a-118">Дескриптор безопасности содержит списки управления доступом (ACL) ресурса.</span><span class="sxs-lookup"><span data-stu-id="3284a-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="3284a-119">В списке ACL указаны разрешения, которые пользователи и группы пользователей имеют доступ к ресурсу».</span><span class="sxs-lookup"><span data-stu-id="3284a-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="3284a-120">Опишите свою подробное описание командлета, но он не должен описывать основные понятия, которые использует командлет.</span><span class="sxs-lookup"><span data-stu-id="3284a-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="3284a-121">Поместите определения концепции в дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="3284a-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="3284a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3284a-122">See Also</span></span>

[<span data-ttu-id="3284a-123">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3284a-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
