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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853720"
---
# <a name="outputtype-attribute-declaration"></a>Объявление атрибута для типа выходных данных

`OutputType` Атрибут определяет типы .NET Framework, возвращаемые командлета, функции или сценарии.

## <a name="syntax"></a>Синтаксис

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Параметры

Тип (`string[]` или `Type[]`) требуется. Указывает типы, возвращаемые функции командлета или сценария.

ParameterSetName (string[]) необязательно. Указывает наборы параметров, возвращающих типы, заданные в `type` параметра.

providerCmdlet необязательно. Указывает командлет поставщика, который возвращает типы, заданные в `type` параметра.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
