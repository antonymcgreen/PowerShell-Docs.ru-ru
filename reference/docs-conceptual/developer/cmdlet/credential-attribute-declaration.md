---
title: Объявление атрибута учетных данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96a5dcad-faed-44d8-8c80-321f10499710
caps.latest.revision: 6
ms.openlocfilehash: 49a62ccb09f06f77862d4737199e58293e7fbe0a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369893"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="0ad50-102">Объявление атрибута учетных данных</span><span class="sxs-lookup"><span data-stu-id="0ad50-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="0ad50-103">Атрибут Credential является необязательным атрибутом, который можно использовать с параметрами учетных данных типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также могла передаваться в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="0ad50-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0ad50-104">При добавлении этого атрибута в объявление параметра Windows PowerShell преобразует входные данные строки в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="0ad50-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="0ad50-105">Например, командлет [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) использует этот атрибут, чтобы создать в Windows PowerShell объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="0ad50-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ad50-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ad50-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="0ad50-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="0ad50-107">Remarks</span></span>

- <span data-ttu-id="0ad50-108">Обычно этот атрибут используется параметрами типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , что позволяет передавать строку в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="0ad50-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="0ad50-109">Когда объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) передается в параметр, Windows PowerShell ничего не делает.</span><span class="sxs-lookup"><span data-stu-id="0ad50-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="0ad50-110">При создании объекта [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) Windows PowerShell использует текущий узел для вывода соответствующих запросов пользователю.</span><span class="sxs-lookup"><span data-stu-id="0ad50-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="0ad50-111">Например, узел по умолчанию отображает запрос на ввод имени пользователя и пароля при использовании этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0ad50-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="0ad50-112">Однако если используется пользовательский узел, который определяет другой запрос, отображается запрос.</span><span class="sxs-lookup"><span data-stu-id="0ad50-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="0ad50-113">Этот атрибут используется с атрибутом Parameter.</span><span class="sxs-lookup"><span data-stu-id="0ad50-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="0ad50-114">Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="0ad50-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="0ad50-115">Атрибут Credential определяется классом [System. Management. Automation. кредентиалаттрибуте](/dotnet/api/System.Management.Automation.CredentialAttribute) .</span><span class="sxs-lookup"><span data-stu-id="0ad50-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ad50-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ad50-116">See Also</span></span>

[<span data-ttu-id="0ad50-117">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="0ad50-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="0ad50-118">Объявление атрибута Parameter</span><span class="sxs-lookup"><span data-stu-id="0ad50-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="0ad50-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ad50-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
