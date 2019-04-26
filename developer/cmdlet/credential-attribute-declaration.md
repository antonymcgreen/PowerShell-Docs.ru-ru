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
ms.openlocfilehash: 49a62ccb09f06f77862d4737199e58293e7fbe0a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068323"
---
# <a name="credential-attribute-declaration"></a>Объявление атрибута учетных данных

Атрибут учетных данных является необязательным атрибутом, который может использоваться с параметрами типа учетных данных [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр. При добавлении этого атрибута к объявлению параметра Windows PowerShell преобразует строковые входные данные в [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объекта. Например [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) командлет использует этот атрибут требуется Windows PowerShell создать [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объект, возвращаемый командлетом.

## <a name="syntax"></a>Синтаксис

```csharp
[Credential]
```

## <a name="remarks"></a>Замечания

- Обычно этот атрибут используется с параметрами типа [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также можно передать в качестве аргумента в параметр. Когда [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объект передается в параметр, Windows PowerShell не выполняет никаких действий.

- При создании [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объекта, Windows PowerShell использует текущий узел для отображения соответствующего приглашения для пользователя. К примеру значение по умолчанию узел запрашивает имя пользователя и пароль при использовании этого атрибута. Тем не менее если используется пользовательский узел, определяющий другую строку, то этот запрос будет отображаться.

- Этот атрибут используется с атрибутом параметра. Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

- Атрибут учетных данных определяется [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) класса.

## <a name="see-also"></a>См. также

[Псевдонимы параметра](./parameter-aliases.md)

[Объявление параметра-атрибут](./parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
