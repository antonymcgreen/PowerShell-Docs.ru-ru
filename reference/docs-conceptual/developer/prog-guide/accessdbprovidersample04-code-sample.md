---
title: Пример кода AccessDbProviderSample04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787280"
---
# <a name="accessdbprovidersample04-code-sample"></a>Пример кода AccessDbProviderSample04

В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).
Этот поставщик работает с хранилищами данных с несколькими уровнями. Для этого типа хранилища данных верхний уровень хранилища содержит корневые элементы, а каждый последующий уровень называется узлом дочерних элементов. Разрешая пользователю работать с этими дочерними узлами, пользователь может выполнять иерархическую работу через хранилище данных.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
