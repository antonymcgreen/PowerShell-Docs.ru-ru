---
ms.date: 09/13/2016
ms.topic: reference
title: Как создать поставщика Windows PowerShell
description: Как создать поставщика Windows PowerShell
ms.openlocfilehash: 51f19bf0dfa5f976a5045ae1342730c8f22f695e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647475"
---
# <a name="how-to-create-a-windows-powershell-provider"></a>Как создать поставщика Windows PowerShell

В этом разделе описывается создание поставщика Windows PowerShell. Поставщик Windows PowerShell можно рассматривать двумя способами. Для пользователя поставщик представляет набор сохраненных данных. Например, хранимые данные могут быть метабазой службы IIS (IIS), реестром Microsoft Windows, файловой системой Windows, Active Directory, а также переменными и псевдонимами данных, хранящимися в Windows PowerShell.

Для разработчика поставщик Windows PowerShell является интерфейсом между пользователем и данными, к которым ему необходим доступ. С этой точки зрения каждый тип поставщика, описанный в этом разделе, поддерживает набор определенных базовых классов и интерфейсов, позволяющих среде выполнения Windows PowerShell предоставлять пользователю определенные командлеты обычным способом.

## <a name="providers-provided-by-windows-powershell"></a>Поставщики, предоставляемые Windows PowerShell

Windows PowerShell предоставляет несколько поставщиков (таких как Поставщик FileSystem, поставщик реестра и поставщик псевдонимов), которые используются для доступа к известным хранилищам данных. Для получения дополнительных сведений о поставщиках, предоставляемых Windows PowerShell, используйте следующую команду для доступа к справке в Интернете:

**>Get-Help в PS about_providers**

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a>Доступ к сохраненным данным с помощью путей Windows PowerShell

Поставщики Windows PowerShell доступны для среды выполнения Windows PowerShell и для команд программным способом с помощью путей Windows PowerShell. В большинстве случаев эти пути используются для прямого доступа к данным через поставщика. Однако некоторые пути могут быть разрешены в внутренние пути, которые позволяют командлету использовать для доступа к данным не Windows PowerShell интерфейсы программирования (API). Дополнительные сведения о работе поставщиков Windows PowerShell в Windows PowerShell см. в разделе [как работает Windows](/previous-versions/ms714658(v=vs.85))PowerShell.

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a>Предоставление командлетов поставщика с помощью дисков Windows PowerShell

Поставщик Windows PowerShell предоставляет свои поддерживаемые командлеты с помощью виртуальных дисков Windows PowerShell.
Windows PowerShell применяет следующие правила для диска Windows PowerShell:

- Имя диска может быть любой буквенно-цифровой последовательности.
- Диск может быть указан в любой допустимой точке пути, называемой "root".
- Диск может быть реализован для любых хранимых данных, а не только для файловой системы.
- Каждый диск сохраняет свое текущее рабочее расположение, позволяя пользователю сохранять контекст при сдвиге между дисками.

## <a name="in-this-section"></a>в этом разделе

В следующей таблице перечислены разделы, в которых содержатся примеры кода, построенные друг от друга. Начиная со второго раздела, базовый поставщик Windows PowerShell можно инициализировать и деинициализировать с помощью среды выполнения Windows PowerShell. следующий раздел добавляет функции для доступа к данным. в следующем разделе приводятся функции для управления данными (элементами в сохраненных данных) и т. д.

|                                                    Раздел                                                    |                                                                                         Определение                                                                                          |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Разработка поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md)               | В этом разделе обсуждаются вещи, которые следует учитывать перед реализацией поставщика Windows PowerShell. В нем перечислены базовые классы и интерфейсы поставщика Windows PowerShell, которые используются. |
| [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md)           | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий среде выполнения Windows PowerShell инициализировать и деинициализировать поставщик.                                        |
| [Создание поставщика дисков Windows PowerShell](./creating-a-windows-powershell-drive-provider.md)           | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю обращаться к хранилищу данных через диск Windows PowerShell.                                                |
| [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md)             | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю управлять элементами в хранилище данных.                                                                  |
| [Создание поставщика контейнеров Windows PowerShell](./creating-a-windows-powershell-container-provider.md)   | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю работать с многослойными хранилищами данных.                                                                        |
| [Создание поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md) | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю перемещаться по элементам хранилища данных иерархически.                                           |
| [Создание поставщика содержимого Windows PowerShell](./creating-a-windows-powershell-content-provider.md)       | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю управлять содержимым элементов в хранилище данных.                                                       |
| [Создание поставщика свойств Windows PowerShell](./creating-a-windows-powershell-property-provider.md)     | В этом разделе показано, как создать поставщик Windows PowerShell, позволяющий пользователю управлять свойствами элементов в хранилище данных.                                                    |

## <a name="see-also"></a>См. также:

[Как работает Windows PowerShell](/previous-versions/ms714658(v=vs.85))

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)
