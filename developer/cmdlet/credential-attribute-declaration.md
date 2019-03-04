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
ms.openlocfilehash: abdd6e915b768b8ac688b6fc8c3194723961765e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863400"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="36614-102">Объявление атрибута учетных данных</span><span class="sxs-lookup"><span data-stu-id="36614-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="36614-103">Атрибут учетных данных является необязательным атрибутом, который может использоваться с параметрами типа учетных данных [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="36614-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="36614-104">При добавлении этого атрибута к объявлению параметра Windows PowerShell преобразует строковые входные данные в [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объекта.</span><span class="sxs-lookup"><span data-stu-id="36614-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="36614-105">Например [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) командлет использует этот атрибут требуется Windows PowerShell создать [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="36614-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>
<span data-ttu-id="36614-106">Атрибут учетных данных является необязательным атрибутом, который может использоваться с параметрами типа учетных данных [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="36614-106">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="36614-107">При добавлении этого атрибута к объявлению параметра Windows PowerShell преобразует строковые входные данные в [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объекта.</span><span class="sxs-lookup"><span data-stu-id="36614-107">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="36614-108">Например [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) командлет использует этот атрибут требуется Windows PowerShell создать [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="36614-108">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="36614-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36614-109">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="36614-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="36614-110">Remarks</span></span>

- <span data-ttu-id="36614-111">Обычно этот атрибут используется с параметрами типа [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="36614-111">Typically this attribute is used by parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="36614-112">Когда [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объект передается в параметр, Windows PowerShell не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="36614-112">When a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="36614-113">При создании [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) объекта, Windows PowerShell использует текущий узел для отображения соответствующего приглашения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="36614-113">When creating the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="36614-114">К примеру значение по умолчанию узел запрашивает имя пользователя и пароль при использовании этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="36614-114">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="36614-115">Тем не менее если используется пользовательский узел, определяющий другую строку, то этот запрос будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="36614-115">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="36614-116">Этот атрибут используется с атрибутом параметра.</span><span class="sxs-lookup"><span data-stu-id="36614-116">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="36614-117">Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="36614-117">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="36614-118">Атрибут учетных данных определяется [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) класса.</span><span class="sxs-lookup"><span data-stu-id="36614-118">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="36614-119">См. также</span><span class="sxs-lookup"><span data-stu-id="36614-119">See Also</span></span>

[<span data-ttu-id="36614-120">Псевдонимы параметра</span><span class="sxs-lookup"><span data-stu-id="36614-120">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="36614-121">Объявление параметра-атрибут</span><span class="sxs-lookup"><span data-stu-id="36614-121">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="36614-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36614-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
