---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: e8890cb6bbe661b8524d83cabf91483acbde8095
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219833"
---
# <a name="troubleshooting-cmdlets"></a>Командлеты для устранения неполадок

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Как разрешить проблему "ПРЕДУПРЕЖДЕНИЕ. Не удалось скачать пакет "имя вашего пакета""?

Нам известно, что на некоторых компьютерах командлеты Install-Module и Update-Module могут завершаться ошибкой.
По результатам нашего расследования это связано с сетевым подключением.
Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.
Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.
Для примера возьмем модуль Azure.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```