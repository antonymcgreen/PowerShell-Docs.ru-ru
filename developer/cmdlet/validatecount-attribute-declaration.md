---
title: Объявление атрибута ValidateCount | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067184"
---
# <a name="validatecount-attribute-declaration"></a>Объявление атрибута ValidateCount

Атрибут ValidateCount указывает минимальное и максимальное число аргументов для параметра командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength` ([System.Int32][]) требуется. Указывает минимальное число аргументов.

`MaxLength`([System.Int32][]) требуется. Указывает максимальное количество аргументов.

## <a name="remarks"></a>Замечания

- Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [Как проверить количество аргументов][].

- Если этот атрибут не вызывается, соответствующего параметра командлета может иметь любое количество аргументов.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

    - `MinLength` И `MaxLength` атрибут параметры не имеют тип [System.Int32][].

    - Значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.

- Атрибут ValidateCount определяется [System.Management.Automation.ValidateCountAttribute][] класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.ValidateCountAttribute][]

[Как проверить количество аргументов][]

[Запись командлета Windows PowerShell][]

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
