---
title: Объявление наборов параметров | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e6d06a9a78356693fe7a338dc5c9207044b23441
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784169"
---
# <a name="how-to-declare-parameter-sets"></a>Как объявить наборы параметров

В этом примере показано, как определить два набора параметров при объявлении параметров для командлета. Каждый набор параметров имеет как уникальный параметр, так и общий параметр, который используется обоими наборами параметров. Дополнительные сведения о наборах параметров, в том числе о том, как указать набор параметров по умолчанию, см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> Везде, где это возможно, определите уникальный параметр набора параметров в качестве обязательного параметра. Однако если вы хотите, чтобы командлет выполнялся без указания каких бы то ни было параметров, параметр UNIQUE может быть необязательным параметром. Например, уникальный параметр `Get-Command` командлета является необязательным.

## <a name="how-to-define-two-parameter-sets"></a>Определение двух наборов параметров

1. Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра первого набора параметров.

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

2. Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра второго набора параметров.

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

3. Для параметра, который принадлежит обоим наборам параметров, добавьте атрибут Parameter для каждого набора параметров, а затем добавьте `ParameterSet` ключевое слово в каждый набор. В каждом атрибуте параметра можно указать способ определения этого параметра. Параметр может быть необязательным в одном наборе и обязателен в другом.

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
