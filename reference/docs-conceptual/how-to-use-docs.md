---
ms.date: 05/22/2020
keywords: powershell,командлет
title: Использование документации по PowerShell
ms.openlocfilehash: 259eb1eea1dc7e8b5ae5730f97c938b838a320bf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808271"
---
# <a name="how-to-use-the-powershell-documentation"></a>Использование документации по PowerShell

Добро пожаловать в интерактивную документацию по PowerShell. Этот сайт содержит справочник по командлетам для следующих версий PowerShell:

- PowerShell 7
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>Поиск статей и выбор версии

Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии. Просто введите слово, которое есть в заголовке статьи. На странице отображается список соответствующих статей. Можно также выбрать вариант поиска по всему сайту из этого списка.

По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell. Некоторые командлеты работают по-разному в различных версиях PowerShell. Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.

Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.

![Средство выбора](media/how-to-use-docs/version-search.gif)

Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`. В следующем примере показаны выходные данные для Windows PowerShell 5.1.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="finding-articles-for-previous-versions"></a>Поиск статей для предыдущих версий

Документация по предыдущим версиям PowerShell сохранена в архиве на сайте [предыдущих версий](https://aka.ms/PSLegacyDocs).

Этот сайт содержит документацию по следующим темам:

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- Рабочие процессы PowerShell
- PowerShell Web Access
