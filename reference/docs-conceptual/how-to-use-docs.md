---
ms.date: 09/25/2019
keywords: powershell,командлет
title: Использование документации по PowerShell
ms.openlocfilehash: 9e3d5828d6bdb4ef14701994f146354a041efaea
ms.sourcegitcommit: a80bb79b85deab8ae3c21de56d1ee432fdd92628
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2019
ms.locfileid: "72281648"
---
# <a name="how-to-use-the-powershell-documentation"></a>Использование документации по PowerShell

Добро пожаловать в интерактивную документацию по PowerShell. Этот сайт содержит справочник по командлетам для следующих версий PowerShell:

- PowerShell 7 (предварительная версия)
- PowerShell 6
- PowerShell 5.1
- PowerShell 5.0
- PowerShell 4.0
- PowerShell 3.0

## <a name="selecting-your-version"></a>Выбор версии

По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell. Некоторые командлеты работают по-разному в различных версиях PowerShell. Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.

Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.

![Средство выбора](images/how-to-use-docs/picker-vall.gif)

Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`. В следующем примере показаны выходные данные для Windows PowerShell 5.1.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="searching-for-articles"></a>Поиск статей

Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии. Просто введите слово, которое есть в заголовке статьи. На странице отображается список соответствующих статей. Можно также выбрать вариант поиска по всему сайту из этого списка.

![Поле фильтра](images/how-to-use-docs/filter-search.gif)
