---
title: Объявление атрибута ValidateLength | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735107"
---
# <a name="validatelength-attribute-declaration"></a>Объявление атрибута ValidateLength

Атрибут ValidateLength указывает минимальное и максимальное количество символов для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength` ([System.Int32](/dotnet/api/System.Int32)) требуется. Указывает минимальное число символов.

`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) требуется. Указывает максимальное допустимое число символов.

## <a name="remarks"></a>Замечания

- Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](./how-to-validate-parameter-input.md).

- Если этот атрибут не используется, что соответствующий аргумент параметра может быть любой длины.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

    - Если значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.

    - Когда `MaxLength` параметр атрибута имеет значение 0.

    - Если аргумент не является строкой.

- Атрибут ValidateLength определяется [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
