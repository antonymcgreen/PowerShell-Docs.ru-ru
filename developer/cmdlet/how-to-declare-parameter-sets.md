---
title: Как объявить наборы параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067898"
---
# <a name="how-to-declare-parameter-sets"></a>Как объявить наборы параметров

В этом примере показано, как определить два набора параметров, при объявлении параметров для командлета. Каждый набор параметров имеет уникальный параметр и общий параметр, который используется в обоих наборах параметров. Дополнительные сведения о наборах параметров, включая способы указания набор параметров по умолчанию, см. в разделе [командлет задает параметр](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> По возможности определите параметр unique командлета набор параметров, что обязательный параметр. Тем не менее если требуется, чтобы командлет для запуска без указания параметров, уникальный параметр может быть необязательный параметр. Например, параметр unique командлета `Get-Command` командлет является необязательным.

## <a name="how-to-define-two-parameter-sets"></a>Как определить два набора параметров

1. Добавление `ParameterSet` слово атрибут параметра для параметра уникальный первого набора параметров.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. Добавление `ParameterSet` ключевое слово, чтобы атрибут параметра для параметр unique командлета второй набор параметров.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. Для параметра, который принадлежит обоих наборов параметров, добавьте атрибут параметра для каждого набора параметров, а затем добавьте `ParameterSet` ключевое слово для каждого набора. В каждом атрибуте параметра можно указать, как определен этот параметр. Параметр может быть необязательным в одном наборе и обязательным в другой.

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a>См. также

[Наборы параметров командлета](./cmdlet-parameter-sets.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
