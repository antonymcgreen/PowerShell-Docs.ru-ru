---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Удаление WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147864"
---
# <a name="uninstallation-instructions"></a>Инструкции по удалению

## <a name="using-command-prompt"></a>Использование командной строки

1. Откройте окно **Командная строка**.
2. Запустите [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) (Автономное средство запуска Центра обновления Windows), как показано ниже:

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

1. Откройте **Панель управления**.
2. Откройте **Программы** и выберите **Удаление программы**.
3. Щелкните **Просмотр установленных обновлений**.
4. Выберите **Windows Management Framework 5.0** в списке установленных обновлений. Это соответствует *KB3134758*, *KB3134759* или *KB3134760*. Щелкните **Удалить**.
