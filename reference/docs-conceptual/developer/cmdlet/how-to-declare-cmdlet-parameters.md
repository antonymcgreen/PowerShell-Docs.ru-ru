---
title: Как объявить параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c0509cc-5a50-49ad-a74f-5527023d0270
caps.latest.revision: 10
ms.openlocfilehash: 80e3e27bcf72b078c192525a843a3b3afb306529
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365683"
---
# <a name="how-to-declare-cmdlet-parameters"></a>Как объявить параметры командлета

В этих примерах показано, как объявить именованные, позиционированные, обязательные, необязательные и параметры Switch. В этих примерах также показано, как определить псевдоним параметра.

## <a name="how-to-declare-a-named-parameter"></a>Как объявить именованный параметр

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра опустите ключевое слово `Position` из атрибута.

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-positional-parameter"></a>Как объявить Позиционированный параметр

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра задайте для ключевого слова `Position` значение, равное положению аргумента. Значение 0 указывает на первую точку.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-mandatory-parameter"></a>Как объявить обязательный параметр

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра задайте для ключевого слова `Mandatory` значение `true`.

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

## <a name="how-to-declare-an-optional-parameter"></a>Как объявить необязательный параметр

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута Parameter опустите ключевое слово `Mandatory`.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>Как объявить параметр Switch

- Определите открытое свойство как Type [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter), а затем объявите атрибут Parameter.

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

Дополнительные сведения об атрибуте Parameter см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-parameter-with-aliases"></a>Как объявить параметр с псевдонимами

- Определите открытое свойство, как показано в следующем коде. Добавьте атрибут Alias, содержащий псевдонимы для параметра. В этом примере для одного и того же параметра определены три псевдонима. Первый псевдоним предоставляет ярлык. Второй и третий псевдонимы предоставляют имена, которые можно использовать для различных сценариев.

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте Alias см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).

## <a name="see-also"></a>См. также:

[System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter)

[Объявление атрибута Parameter](./parameter-attribute-declaration.md)

[Объявление атрибута Alias](./alias-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
