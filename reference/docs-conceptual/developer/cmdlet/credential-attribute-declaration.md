---
title: Объявление атрибута учетных данных | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a6deca52fa6c9e46138ae92401f58ac5dbd15852
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784373"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="91618-102">Объявление атрибута учетных данных</span><span class="sxs-lookup"><span data-stu-id="91618-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="91618-103">Атрибут Credential является необязательным атрибутом, который можно использовать с параметрами учетных данных типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также могла передаваться в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="91618-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="91618-104">При добавлении этого атрибута в объявление параметра Windows PowerShell преобразует входные данные строки в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="91618-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="91618-105">Например, командлет [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) использует этот атрибут, чтобы создать в Windows PowerShell объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="91618-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="91618-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91618-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="91618-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="91618-107">Remarks</span></span>

- <span data-ttu-id="91618-108">Обычно этот атрибут используется параметрами типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , что позволяет передавать строку в качестве аргумента в параметр.</span><span class="sxs-lookup"><span data-stu-id="91618-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="91618-109">Когда объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) передается в параметр, Windows PowerShell ничего не делает.</span><span class="sxs-lookup"><span data-stu-id="91618-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="91618-110">При создании объекта [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) Windows PowerShell использует текущий узел для вывода соответствующих запросов пользователю.</span><span class="sxs-lookup"><span data-stu-id="91618-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="91618-111">Например, узел по умолчанию отображает запрос на ввод имени пользователя и пароля при использовании этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="91618-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="91618-112">Однако если используется пользовательский узел, который определяет другой запрос, отображается запрос.</span><span class="sxs-lookup"><span data-stu-id="91618-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="91618-113">Этот атрибут используется с атрибутом Parameter.</span><span class="sxs-lookup"><span data-stu-id="91618-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="91618-114">Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="91618-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="91618-115">Атрибут Credential определяется классом [System. Management. Automation. кредентиалаттрибуте](/dotnet/api/System.Management.Automation.CredentialAttribute) .</span><span class="sxs-lookup"><span data-stu-id="91618-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="91618-116">См. также</span><span class="sxs-lookup"><span data-stu-id="91618-116">See Also</span></span>

[<span data-ttu-id="91618-117">Псевдонимы параметров</span><span class="sxs-lookup"><span data-stu-id="91618-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="91618-118">Объявление атрибута параметра</span><span class="sxs-lookup"><span data-stu-id="91618-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="91618-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91618-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
