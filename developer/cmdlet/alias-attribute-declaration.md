---
title: Объявление атрибута псевдоним | Документация Майкрософт
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068725"
---
# <a name="alias-attribute-declaration"></a>Объявление атрибута псевдонима

Alias-атрибут позволяет пользователю указать другие имена для параметра командлета. Псевдонимы могут использоваться для предоставления ярлыков для имени параметра, или они могут предоставлять разные имена, которые подходят для разных сценариев.

## <a name="syntax"></a>Синтаксис

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Параметры

`aliasName` (String[]) Обязательно. Задает набор имен с разделителями запятыми псевдоним для параметра командлета.

## <a name="remarks"></a>Замечания

- Alias-атрибут используется с атрибутом параметр, при указании параметра командлета. Дополнительные сведения о том, как объявить этих атрибутов см. в разделе [как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md).

- Каждое имя псевдонима должно быть уникальным в пределах командлета. Windows PowerShell не проверяет наличие повторяющихся псевдонимов.

- Alias-атрибут используется один раз для каждого параметра в командлет.

- Alias-атрибут определяется [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) класса.

## <a name="see-also"></a>См. также

[Псевдонимы параметра](./parameter-aliases.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
