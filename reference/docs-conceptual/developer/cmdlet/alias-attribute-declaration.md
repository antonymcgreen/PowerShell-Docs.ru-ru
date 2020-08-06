---
title: Объявление атрибута Alias | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782418"
---
# <a name="alias-attribute-declaration"></a>Объявление атрибута псевдонима

Атрибут Alias позволяет пользователю указать различные имена для параметра командлета. Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.

## <a name="syntax"></a>Синтаксис

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Параметры

`aliasName`(String []) Обязательно. Задает набор разделенных запятыми имен псевдонимов для параметра командлета.

## <a name="remarks"></a>Примечания

- Атрибут Alias используется с атрибутом Parameter при указании параметра командлета. Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).

- Каждое имя псевдонима должно быть уникальным в пределах командлета. Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.

- Атрибут Alias используется один раз для каждого параметра в командлете.

- Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .

## <a name="see-also"></a>См. также

[Псевдонимы параметров](./parameter-aliases.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
