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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369893"
---
# <a name="credential-attribute-declaration"></a>Объявление атрибута учетных данных

Атрибут Credential является необязательным атрибутом, который можно использовать с параметрами учетных данных типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также могла передаваться в качестве аргумента в параметр. При добавлении этого атрибута в объявление параметра Windows PowerShell преобразует входные данные строки в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) . Например, командлет [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) использует этот атрибут, чтобы создать в Windows PowerShell объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , возвращаемый командлетом.

## <a name="syntax"></a>Синтаксис

```csharp
[Credential]
```

## <a name="remarks"></a>Замечания

- Обычно этот атрибут используется параметрами типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , что позволяет передавать строку в качестве аргумента в параметр. Когда объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) передается в параметр, Windows PowerShell ничего не делает.

- При создании объекта [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) Windows PowerShell использует текущий узел для вывода соответствующих запросов пользователю. Например, узел по умолчанию отображает запрос на ввод имени пользователя и пароля при использовании этого атрибута. Однако если используется пользовательский узел, который определяет другой запрос, отображается запрос.

- Этот атрибут используется с атрибутом Parameter. Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

- Атрибут Credential определяется классом [System. Management. Automation. кредентиалаттрибуте](/dotnet/api/System.Management.Automation.CredentialAttribute) .

## <a name="see-also"></a>См. также:

[Псевдонимы параметров](./parameter-aliases.md)

[Объявление атрибута Parameter](./parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
