---
title: Объявление наборов параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365613"
---
# <a name="how-to-declare-parameter-sets"></a>Как объявить наборы параметров

В этом примере показано, как определить два набора параметров при объявлении параметров для командлета. Каждый набор параметров имеет как уникальный параметр, так и общий параметр, который используется обоими наборами параметров. Дополнительные сведения о наборах параметров, в том числе о том, как указать набор параметров по умолчанию, см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> Везде, где это возможно, определите уникальный параметр набора параметров в качестве обязательного параметра. Однако если вы хотите, чтобы командлет выполнялся без указания каких бы то ни было параметров, параметр UNIQUE может быть необязательным параметром. Например, параметр Unique командлета `Get-Command` является необязательным.

## <a name="how-to-define-two-parameter-sets"></a>Определение двух наборов параметров

1. Добавьте ключевое слово `ParameterSet` в атрибут Parameter для уникального параметра первого набора параметров.

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

2. Добавьте ключевое слово `ParameterSet` в атрибут Parameter для уникального параметра второго набора параметров.

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

3. Для параметра, который принадлежит обоим наборам параметров, добавьте атрибут Parameter для каждого набора параметров, а затем добавьте к каждому набору ключевое слово `ParameterSet`. В каждом атрибуте параметра можно указать способ определения этого параметра. Параметр может быть необязательным в одном наборе и обязателен в другом.

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

## <a name="see-also"></a>См. также:

[Наборы параметров командлета](./cmdlet-parameter-sets.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
