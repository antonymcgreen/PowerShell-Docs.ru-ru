---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: Запрос на принятие условий лицензии для сценариев
ms.openlocfilehash: e7101eb6a480dd87965b7b9be9d49583042b603f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084680"
---
# <a name="requiring-license-acceptance-for-scripts"></a>Запрос на принятие условий лицензии для сценариев

Для скриптов процедура принятия условий лицензионного соглашения не поддерживается. Но поддерживается вариант, при котором скрипт зависит от модуля, для использования которого требуется принять условия лицензионного соглашения.

Команды скрипта (Install-Script/Save-Script/Update-Script) поддерживают новый параметр -AcceptLicense. Его поведение аналогично действиям пользователя после прочтения лицензионного соглашения. Если параметр -AcceptLicense не указан, для пользователя будет отображаться файл license.txt зависимого модуля и запрос на принятие условий лицензионного соглашения.

## <a name="examples"></a>ПРИМЕРЫ

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a>Пример 1: установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения

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

## <a name="more-details"></a>Дополнительные подробности

- [Поддержка запроса на принятие условий лицензионного соглашения для модулей](module-license-acceptance.md)
- [Поддержка запроса на принятие условий лицензионного соглашения в коллекции PowerShell](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../how-to/working-with-packages/deploy-to-azure-automation.md)
