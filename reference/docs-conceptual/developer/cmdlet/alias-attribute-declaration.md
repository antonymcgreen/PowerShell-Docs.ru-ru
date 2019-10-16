---
title: Объявление атрибута Alias | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.assetid: d0df3a46-b1cc-42b9-beb1-e16bce254007
caps.latest.revision: 10
ms.openlocfilehash: 4d20672c5181c994c1b53624f6c42a301db11f26
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370023"
---
# <a name="alias-attribute-declaration"></a>Объявление атрибута псевдонима

Атрибут Alias позволяет пользователю указать различные имена для параметра командлета. Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.

## <a name="syntax"></a>Синтаксис

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Параметры

Требуется `aliasName` (String []). Задает набор разделенных запятыми имен псевдонимов для параметра командлета.

## <a name="remarks"></a>Замечания

- Атрибут Alias используется с атрибутом Parameter при указании параметра командлета. Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).

- Каждое имя псевдонима должно быть уникальным в пределах командлета. Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.

- Атрибут Alias используется один раз для каждого параметра в командлете.

- Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .

## <a name="see-also"></a>См. также:

[Псевдонимы параметров](./parameter-aliases.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
