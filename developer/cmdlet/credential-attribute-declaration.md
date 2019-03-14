---
title: Учетные данные объявление атрибута | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96a5dcad-faed-44d8-8c80-321f10499710
caps.latest.revision: 6
ms.openlocfilehash: 1513d340cdadc5cb7622e791cc3c163ff39dfe1d
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795408"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="0fb30-102">Объявление атрибута учетных данных</span><span class="sxs-lookup"><span data-stu-id="0fb30-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="0fb30-103">Атрибут учетных данных является необязательным атрибутом, который может использоваться с параметрами типа учетных данных [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="0fb30-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0fb30-104">При добавлении этого атрибута к объявлению параметра Windows PowerShell преобразует строковые входные данные в [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объекта.</span><span class="sxs-lookup"><span data-stu-id="0fb30-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="0fb30-105">Например [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) командлет использует этот атрибут требуется Windows PowerShell создать [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="0fb30-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fb30-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fb30-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="0fb30-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="0fb30-107">Remarks</span></span>

- <span data-ttu-id="0fb30-108">Обычно этот атрибут используется с параметрами типа [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="0fb30-108">Typically this attribute is used by parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0fb30-109">Когда [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объект передается в параметр, Windows PowerShell не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="0fb30-109">When a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="0fb30-110">При создании [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объекта, Windows PowerShell использует текущий узел для отображения соответствующего приглашения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fb30-110">When creating the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="0fb30-111">К примеру значение по умолчанию узел запрашивает имя пользователя и пароль при использовании этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0fb30-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="0fb30-112">Тем не менее если используется пользовательский узел, определяющий другую строку, то этот запрос будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="0fb30-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="0fb30-113">Этот атрибут используется с атрибутом параметра.</span><span class="sxs-lookup"><span data-stu-id="0fb30-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="0fb30-114">Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="0fb30-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="0fb30-115">Атрибут учетных данных определяется [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="0fb30-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fb30-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0fb30-116">See Also</span></span>

[<span data-ttu-id="0fb30-117">Псевдонимы параметра</span><span class="sxs-lookup"><span data-stu-id="0fb30-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="0fb30-118">Объявление параметра-атрибут</span><span class="sxs-lookup"><span data-stu-id="0fb30-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="0fb30-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fb30-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
