---
title: Объявление атрибута OutputType | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786549"
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
