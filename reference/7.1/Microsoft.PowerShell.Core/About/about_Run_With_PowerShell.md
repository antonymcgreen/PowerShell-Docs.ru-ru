---
description: Описание использования функции "Запуск с помощью PowerShell" для выполнения сценария с диска файловой системы.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: 83931fcfcc89340b1d4958e41cb182642a554737
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232522"
---
# <a name="about-run-with-powershell"></a>Сведения о запуске с помощью PowerShell

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описание использования функции "Запуск с помощью PowerShell" для выполнения сценария с диска файловой системы.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Начиная с Windows PowerShell 3,0, можно использовать функцию "Запуск с помощью PowerShell" для запуска сценариев из проводника в Windows 8, Windows Server 2012 и Windows Explorer в более ранних версиях Windows.

Функция "запустить с помощью PowerShell" предназначена для выполнения скриптов, которые не имеют обязательных параметров и не возвращают выходные данные в командную строку.

При использовании функции "Запуск с помощью PowerShell" окно консоли PowerShell появляется только вкратце, если вообще. Вы не можете взаимодействовать с ним.

Чтобы использовать функцию "Запуск с помощью PowerShell", сделайте следующее:

В проводнике (или в проводнике Windows) щелкните правой кнопкой мыши имя файла скрипта и выберите команду "запустить с помощью PowerShell".

Функция "запустить с помощью PowerShell" запускает сеанс PowerShell с политикой выполнения "обход", запускает сценарий и закрывает сеанс.

Она выполняет команду, имеющую следующий формат:

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

"Запустить с помощью PowerShell" задает политику выполнения обхода только для сеанса (текущего экземпляра процесса PowerShell), в котором выполняется скрипт.
Эта функция не изменяет политику выполнения для компьютера или пользователя.

На функцию "Запуск с помощью PowerShell" влияет только политика выполнения AllSigned. Если политика выполнения AllSigned действует для компьютера или пользователя, "запустить с помощью PowerShell" запускает только подписанные сценарии. На запуск с PowerShell не влияют никакие другие политики выполнения. Подробнее см. в разделе [about_Execution_Policies](about_Execution_Policies.md).

Устранение неполадок Примечание. команда выполнить с PowerShell может запросить подтверждение изменения политики выполнения.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Execution_Policies](about_Execution_Policies.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Scripts](about_Scripts.md)

