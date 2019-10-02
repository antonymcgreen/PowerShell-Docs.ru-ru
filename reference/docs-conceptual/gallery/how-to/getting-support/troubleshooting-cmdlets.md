---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: f5cd9c0cc23fef5891bf02c10b6541ab0f9d418a
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328305"
---
# <a name="troubleshooting-cmdlets"></a>Командлеты для устранения неполадок

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"

Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.
По результатам нашего расследования это связано с сетевым подключением.
Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.
Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.
Для примера возьмем модуль Azure.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```
