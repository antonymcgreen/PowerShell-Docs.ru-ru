---
ms.date: 06/12/2017
title: Удаление WMF 5.0
description: В этой статье описывается, как удалить WMF из старых версий Windows.
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660804"
---
# <a name="uninstallation-instructions"></a>Инструкции по удалению

## <a name="using-command-prompt"></a>Использование командной строки

1. Откройте **командную строку**.
2. Запустите [Автономное средство запуска Центра обновления Windows](https://support.microsoft.com/kb/934307), как показано ниже:

В Windows Server 2012 R2 и Windows 8.1:

```powershell
wusa /uninstall /kb:3134758
```

В Windows Server 2012:

```powershell
wusa /uninstall /kb:3134759
```

В Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1):

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a>Использование панели управления

1. Откройте **панель управления**.
2. Откройте раздел **Программы** и выберите **Удаление программы**.
3. Щелкните **Просмотр установленных обновлений**.
4. Выберите **Windows Management Framework 5.0** в списке установленных обновлений. Это соответствует *KB3134758* , *KB3134759* или *KB3134760*. Щелкните **Удалить**.
