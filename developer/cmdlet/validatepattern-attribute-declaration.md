---
title: Объявление атрибута ValidatePattern | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067133"
---
# <a name="validatepattern-attribute-declaration"></a>Объявление атрибута ValidatePattern

Атрибут ValidatePattern указывает шаблон регулярного выражения, проверяет корректность аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

При вызове командлета ValidatePattern, среда выполнения Windows PowerShell Преобразует аргумент параметра командлета в строку и затем сравнивает эту строку в шаблоне, указанного в атрибуте ValidatePattern. Командлет выполняется только в том случае, если преобразованное строковое представление аргумента и указанному шаблону соответствует. Если они не совпадают, сообщение об ошибке средой выполнения Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>Параметры

`RegexString` ([System.String](/dotnet/api/System.String)) требуется. Указывает регулярное выражение, которое проверяет аргумент параметра.

Параметры ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр. Задает побитовое сочетание [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) флаги, определяющие параметры регулярных выражений.

## <a name="remarks"></a>Замечания

- Этот атрибут может использоваться только один раз на параметр.

- Можно использовать `Option` параметр атрибута, чтобы более детально определить шаблон. Например можно сделать шаблон с учетом регистра.

- Если этот атрибут применяется к коллекции, каждый элемент в коллекции должно соответствовать шаблону.

- Атрибут ValidatePattern определяется [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
