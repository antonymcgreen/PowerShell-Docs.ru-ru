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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059173"
---
# <a name="how-to-declare-cmdlet-parameters"></a>Как объявить параметры командлета

Эти примеры показывают, как объявить именованный, позиционные, необходимые, необязательные и параметры-переключатели. Этих примерах также показано, как определить псевдоним параметра.

## <a name="how-to-declare-a-named-parameter"></a>Как объявить именованный параметр

- Определите общедоступное свойство, как показано в следующем коде. При добавлении атрибут Parameter, опустите `Position` ключевое слово из атрибута.

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-positional-parameter"></a>Как объявить позиционного параметра

- Определите общедоступное свойство, как показано в следующем коде. При добавлении атрибут Parameter установите `Position` ключевое слово в позицию аргумента. Значение 0 указывает первую позицию.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-mandatory-parameter"></a>Как объявить обязательный параметр

- Определите общедоступное свойство, как показано в следующем коде. При добавлении атрибут Parameter установите `Mandatory` ключевое слово `true`.

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

## <a name="how-to-declare-an-optional-parameter"></a>Как объявить необязательный параметр

- Определите общедоступное свойство, как показано в следующем коде. При добавлении атрибут Parameter, опустите `Mandatory` ключевое слово.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>Как объявить параметр-переключатель

- Определить открытое свойство в качестве типа [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), а затем объявить атрибут Parameter.

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

Дополнительные сведения об атрибуте параметров см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-parameter-with-aliases"></a>Способ объявления параметра с псевдонимами

- Определите общедоступное свойство, как показано в следующем коде. Добавьте атрибут псевдоним, который выводит список псевдонимов для параметра. В этом примере три псевдонима определены для одного параметра. Первый псевдоним существует сочетание клавиш. Второй и третий псевдонимы предоставляют имена, которые можно использовать для разных сценариев.

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

Дополнительные сведения об атрибуте псевдонима см. в разделе [объявление атрибута псевдоним](./alias-attribute-declaration.md).

## <a name="see-also"></a>См. также

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[Объявление параметра-атрибут](./parameter-attribute-declaration.md)

[Атрибут объявления псевдонима](./alias-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
