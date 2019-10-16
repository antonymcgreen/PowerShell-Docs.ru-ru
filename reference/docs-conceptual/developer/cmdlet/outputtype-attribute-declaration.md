---
title: Объявление атрибута OutputType | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365343"
---
# <a name="outputtype-attribute-declaration"></a>Объявление атрибута для типа выходных данных

Атрибут `OutputType` определяет типы .NET Framework, возвращаемые командлетом, функцией или скриптом.

## <a name="syntax"></a>Синтаксис

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Параметры

Требуется тип (`string[]` или `Type[]`). Указывает типы, возвращаемые функцией командлета или скриптом.

Параметерсетнаме (String []) необязательный. Задает наборы параметров, которые возвращают типы, указанные в параметре `type`.

Провидеркмдлет необязательный. Указывает командлет поставщика, возвращающий типы, указанные в параметре `type`.

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
