---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута для типа выходных данных
description: Объявление атрибута для типа выходных данных
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646466"
---
# <a name="outputtype-attribute-declaration"></a>Объявление атрибута для типа выходных данных

`OutputType`Атрибут определяет типы .NET Framework, возвращаемые командлетом, функцией или скриптом.

## <a name="syntax"></a>Синтаксис

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Параметры

`string[]`Обязательный тип (или `Type[]` ). Указывает типы, возвращаемые функцией командлета или скриптом.

Параметерсетнаме (String []) необязательный. Задает наборы параметров, которые возвращают типы, указанные в `type` параметре.

Провидеркмдлет необязательный. Указывает командлет поставщика, возвращающий типы, указанные в `type` параметре.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
