---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72352110"
---
# <a name="troubleshooting-cmdlets"></a>Командлеты для устранения неполадок

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"

Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой. По результатам нашего расследования это связано с сетевым подключением. Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты. Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль. Для примера возьмем модуль Azure.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a>Требуемые сетевые конечные точки

Для командлетов Install и Update требуется доступ к Интернету для подключения к конечным точкам сети, используемым коллекцией PowerShell. Убедитесь, что политики сетевого доступа позволяют подключаться к приведенным ниже конечным точкам.

- oneget.org
- go.microsoft.com
- az818661.vo.msecnd.net
- [www.powershellgallery.com](www.powershellgallery.com)
- devopsgallerystorage.blob.core.windows.net
