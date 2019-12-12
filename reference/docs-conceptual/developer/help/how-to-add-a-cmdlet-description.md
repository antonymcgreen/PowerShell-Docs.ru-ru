---
title: Добавление описания командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361283"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="f3f8d-102">Как добавить описание командлета</span><span class="sxs-lookup"><span data-stu-id="f3f8d-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="f3f8d-103">В этом разделе описывается добавление содержимого, которое отображается в разделе Описание справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-103">This section describes how to add content that is displayed in the DESCRIPTION section of the cmdlet Help.</span></span> <span data-ttu-id="f3f8d-104">В файле справки это содержимое добавляется в узел команды для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f3f8d-105">Для получения полного представления файла справки откройте один из файлов длл-Хелп. XML, расположенный в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="f3f8d-106">Например, файл Microsoft. PowerShell. Commands. Management. длл-Хелп. XML содержит содержимое для некоторых командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="f3f8d-107">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="f3f8d-107">To Add a Description</span></span>

- <span data-ttu-id="f3f8d-108">Начните с объяснения основных функций командлета более подробно.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="f3f8d-109">Во многих случаях можно объяснить термины, используемые в имени командлета, и проиллюстрировать неизвестные концепции с помощью примера.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="f3f8d-110">Например, если командлет добавляет данные в файл, объясните, что он добавляет данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="f3f8d-111">Чтобы найти все функции командлета, ознакомьтесь со списком параметров.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="f3f8d-112">Опишите основную функцию командлета, а затем включите другие функции и функции.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="f3f8d-113">Например, если основной функцией командлета является изменение одного свойства, но командлет может изменить все свойства, скажем, в подробном описании.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="f3f8d-114">Если параметры командлета позволяют пользователям запросить информацию различными способами, объясните их.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="f3f8d-115">Включите сведения о способах, с помощью которых пользователи могут использовать командлет, в дополнение к очевидным применениям.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="f3f8d-116">Например, можно использовать объект, извлекаемый командлетом `Get-Host`, чтобы изменить цвет текста в командном окне Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="f3f8d-117">Пример: "командлет `Get-Acl` получает объекты, представляющие дескриптор безопасности файла или ресурса.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-117">Example:  "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="f3f8d-118">Дескриптор безопасности содержит списки управления доступом (ACL) ресурса.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="f3f8d-119">Список ACL задает разрешения, которые пользователи и группы пользователей должны иметь к ресурсу. "</span><span class="sxs-lookup"><span data-stu-id="f3f8d-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="f3f8d-120">Подробное описание должно описывать командлет, но не должно описывать концепции, используемые командлетом.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="f3f8d-121">Помещайте определения концепций в дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="f3f8d-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3f8d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3f8d-122">See Also</span></span>

[<span data-ttu-id="f3f8d-123">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3f8d-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
