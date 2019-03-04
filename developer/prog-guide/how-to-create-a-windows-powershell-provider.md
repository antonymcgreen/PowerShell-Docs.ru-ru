---
title: Как создать поставщик Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide]
- providers [PowerShellProgrammer's Guide], creating
- Windows PowerShell Programmer's Guide, providers
ms.assetid: 863e48e9-7206-4c6a-a59a-2ab2d30396bc
caps.latest.revision: 5
ms.openlocfilehash: a114a4b0d5a5bfcc0d072f83f0e59ca6d329a172
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862410"
---
# <a name="how-to-create-a-windows-powershell-provider"></a>Как создать поставщика Windows PowerShell

В этом разделе описывается, как построить поставщик Windows PowerShell. Поставщик Windows PowerShell можно считать двумя способами. Пользователю поставщик представляет набор сохраненных данных. Например сохраненных данных может быть метабазы Internet Information Services (IIS), реестра Microsoft Windows, в файловой системе Windows, Active Directory и данные переменной и псевдоним, хранящихся в Windows PowerShell.

Для разработчика поставщик Windows PowerShell — это интерфейс между пользователем и данные, необходимые пользователю для доступа к. С этой точки зрения каждого типа поставщика, описанные в этом разделе поддерживает ряд определенных базовые классы и интерфейсы, позволяющие среды выполнения Windows PowerShell для предоставления определенных командлетов пользователю одинаковым образом.

## <a name="providers-provided-by-windows-powershell"></a>Поставщики, предоставляемые Windows PowerShell

Windows PowerShell предоставляет несколько поставщиков (например, поставщик FileSystem, поставщик реестра и поставщик Alias), которые используются для доступа к хранилищам известных данных. Дополнительные сведения о поставщиках, предоставляемые Windows PowerShell используйте следующую команду, чтобы открыть интерактивную справку:

**PS>get-help about_provider**

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a>Доступ к сохраненных данных, с помощью путей Windows PowerShell

Поставщики Windows PowerShell доступны в среду выполнения Windows PowerShell и командами программным способом при помощи пути Windows PowerShell. В большинстве случаев, эти пути используются для прямого доступа к данным через поставщика. Тем не менее некоторые пути можно привести к поставщик внутреннего пути, чтобы командлет, чтобы использовать Windows PowerShell прикладного программирования (API) для доступа к данным. Дополнительные сведения о том, как работают поставщики Windows PowerShell в Windows PowerShell, см. в разделе [как Windows PowerShell работает](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).
Поставщики Windows PowerShell доступны в среду выполнения Windows PowerShell и командами программным способом при помощи пути Windows PowerShell. В большинстве случаев, эти пути используются для прямого доступа к данным через поставщика. Тем не менее некоторые пути можно привести к поставщик внутреннего пути, чтобы командлет, чтобы использовать Windows PowerShell прикладного программирования (API) для доступа к данным. Дополнительные сведения о том, как работают поставщики Windows PowerShell в Windows PowerShell, см. в разделе [как Windows PowerShell работает](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a>Диски предоставления командлетов поставщика, с помощью Windows PowerShell

Поставщик Windows PowerShell предоставляет его поддерживаемых командлетов, с помощью виртуальных дисков Windows PowerShell. Windows PowerShell применяются следующие правила для диска Windows PowerShell:

- Имя диска может быть любой буквенно-цифровой последовательности.

- Диск можно указать любой допустимый момент на путь, с именем «root».

- Диск может быть реализован для хранимых данных, не только в файловой системе.

- Каждый диск сохраняет свой собственный текущему рабочему расположению, позволяя пользователю сохранить контекст, при сдвиге между дисками.

## <a name="in-this-section"></a>Содержание

В следующей таблице перечислены разделы, содержащие примеры кода, которые зависят друг от друга. Начиная со второго раздела, базовый поставщик Windows PowerShell можно инициализировать и не инициализирована средой выполнения Windows PowerShell, следующий раздел добавляет функциональные возможности для доступа к данным, функции для работы с данные (добавляет следующий раздел элементы в сохраненных данных), и т. д.

|Раздел|Определение|
|-----------|----------------|
|[Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)|В этом разделе рассматриваются действия, которые следует учитывать перед реализацией поставщика Windows PowerShell. Приводятся сведения о Windows PowerShell поставщика базовые классы и интерфейсы, которые используются.|
|[Создание поставщика базовый Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет среде выполнения Windows PowerShell для инициализации и инициализации поставщика.|
|[Создание поставщика Windows PowerShell диска](./creating-a-windows-powershell-drive-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет пользователю получить доступ к хранилищу данных через диск Windows PowerShell.|
|[Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет пользователю для работы с элементами в хранилище данных.|
|[Создание контейнера поставщика Windows PowerShell](./creating-a-windows-powershell-container-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет пользователю работать в хранилищах данных многоуровневый.|
|[Создание поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет пользователю переходить элементы хранилища данных в иерархическом виде.|
|[Создание поставщика Windows PowerShell содержимого](./creating-a-windows-powershell-content-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который служит для управления содержимым элементов в хранилище данных.|
|[Создание поставщика Windows PowerShell свойства](./creating-a-windows-powershell-property-provider.md)|В этом разделе показано, как создать поставщик Windows PowerShell, который позволяет пользователю управлять свойств элементов в хранилище данных.|

## <a name="see-also"></a>См. также

[Как работает Windows PowerShell](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Как работает Windows PowerShell](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)