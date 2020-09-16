---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Удаление WMF 5.0
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236311"
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
4. Выберите **Windows Management Framework 5.0** в списке установленных обновлений. Это соответствует *KB3134758*, *KB3134759* или *KB3134760*. Щелкните **Удалить**.
