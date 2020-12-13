---
ms.date: 09/13/2016
ms.topic: reference
title: Как объявить параметры командлета
description: Как объявить параметры командлета
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667102"
---
# <a name="how-to-declare-cmdlet-parameters"></a>Как объявить параметры командлета

В этих примерах показано, как объявить именованные, позиционированные, обязательные, необязательные и параметры Switch. В этих примерах также показано, как определить псевдоним параметра.

## <a name="how-to-declare-a-named-parameter"></a>Как объявить именованный параметр

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра опустите `Position` ключевое слово из атрибута.

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

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута Parameter задайте `Position` для ключевого слова значение, равное положению аргумента. Значение 0 указывает на первую точку.

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

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра задайте `Mandatory` для ключевого слова значение `true` .

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

- Определите открытое свойство, как показано в следующем коде. При добавлении атрибута параметра опустите `Mandatory` ключевое слово.

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

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[Объявление атрибута параметра](./parameter-attribute-declaration.md)

[Объявление атрибута псевдонима](./alias-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
