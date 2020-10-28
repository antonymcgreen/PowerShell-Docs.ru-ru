---
ms.date: 07/29/2020
keywords: powershell,командлет
title: Использование документации по PowerShell
description: В этой статье описывается, как использовать функции данного сайта, включая фильтрацию при поиске и выбор версий.
ms.openlocfilehash: 32f0c613e10329cc4830386b744e766eeeab0187
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501122"
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

![Использование средства выбора версий](media/how-to-use-docs/version-search.gif)

Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`. В следующем примере показаны выходные данные для Windows PowerShell 5.1.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

Если вы не знакомы с PowerShell и вам нужна помощь в понимании синтаксиса команды, см. раздел [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).

## <a name="finding-articles-for-previous-versions"></a>Поиск статей для предыдущих версий

Документация по предыдущим версиям PowerShell сохранена в архиве на сайте [предыдущих версий](https://aka.ms/PSLegacyDocs).

Этот сайт содержит документацию по следующим темам:

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- Рабочие процессы PowerShell
- PowerShell Web Access
