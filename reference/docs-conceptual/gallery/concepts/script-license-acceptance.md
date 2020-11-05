---
ms.date: 06/09/2017
title: Запрос на принятие условий лицензии для сценариев
description: В этой статье описывается, как работать со скриптами, опубликованными в коллекции PowerShell, которые требуют принятия лицензии пользователя.
ms.openlocfilehash: d82974810fd1e73ef8d9e5771fc430d0f7964e87
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656087"
---
# <a name="requiring-license-acceptance-for-scripts"></a>Запрос на принятие условий лицензии для сценариев

Для скриптов процедура принятия условий лицензионного соглашения не поддерживается. Но поддерживается вариант, при котором скрипт зависит от модуля, для использования которого требуется принять условия лицензионного соглашения.

Команды скрипта PowerShellGet поддерживают параметр **AcceptLicense** , поведение которого аналогично поведению при принятии пользователем лицензии. Если параметр **AcceptLicense** не указан, пользователю отображается файл `license.txt` для зависимого модуля и выводится запрос на принятие лицензии.

## <a name="examples"></a>Примеры

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a>Пример 1. Установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения

Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance. Пользователю предлагается принять условия лицензионного соглашения.

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance

License Acceptance
MIT License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a>Пример 2. Установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения и указать -AcceptLicense

Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance. Пользователю не предлагается принять условия лицензии, так как указан параметр -AcceptLicense.

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a>Дополнительные сведения

- [Поддержка запроса на принятие условий лицензионного соглашения для модулей](module-license-acceptance.md)
- [Поддержка запроса на принятие условий лицензионного соглашения в коллекции PowerShell](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../how-to/working-with-packages/deploy-to-azure-automation.md)
