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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067609"
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
