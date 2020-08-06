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
# <a name="credential-attribute-declaration"></a>Объявление атрибута учетных данных

Атрибут Credential является необязательным атрибутом, который можно использовать с параметрами учетных данных типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , чтобы строка также могла передаваться в качестве аргумента в параметр. При добавлении этого атрибута в объявление параметра Windows PowerShell преобразует входные данные строки в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) . Например, командлет [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) использует этот атрибут, чтобы создать в Windows PowerShell объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , возвращаемый командлетом.

## <a name="syntax"></a>Синтаксис

```csharp
[Credential]
```

## <a name="remarks"></a>Примечания

- Обычно этот атрибут используется параметрами типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) , что позволяет передавать строку в качестве аргумента в параметр. Когда объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) передается в параметр, Windows PowerShell ничего не делает.

- При создании объекта [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) Windows PowerShell использует текущий узел для вывода соответствующих запросов пользователю. Например, узел по умолчанию отображает запрос на ввод имени пользователя и пароля при использовании этого атрибута. Однако если используется пользовательский узел, который определяет другой запрос, отображается запрос.

- Этот атрибут используется с атрибутом Parameter. Дополнительные сведения об этом атрибуте см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

- Атрибут Credential определяется классом [System. Management. Automation. кредентиалаттрибуте](/dotnet/api/System.Management.Automation.CredentialAttribute) .

## <a name="see-also"></a>См. также

[Псевдонимы параметров](./parameter-aliases.md)

[Объявление атрибута параметра](./parameter-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
