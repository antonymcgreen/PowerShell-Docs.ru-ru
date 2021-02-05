---
ms.date: 01/25/2021
title: Командлеты для устранения неполадок
description: В этой статье приведены сведения и шаги по устранению ошибок с помощью коллекции PowerShell.
ms.openlocfilehash: 8139147683b655b5f8532c3068387db6df12a98f
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771820"
---
# <a name="troubleshooting-cmdlets"></a>Командлеты для устранения неполадок

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"

Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой. По результатам нашего расследования это связано с сетевым подключением. Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты. Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль. Для примера возьмем модуль Azure.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a>Требуемые сетевые конечные точки

Для командлетов Install и Update требуется доступ к Интернету для подключения к конечным точкам сети, используемым коллекцией PowerShell. Убедитесь, что политики сетевого доступа позволяют подключаться к приведенным ниже конечным точкам.

- `psg-prod-eastus.azureedge.net` — имя узла CDN;
- `az818661.vo.msecnd.net` — имя узла CDN;
- `devopsgallerystorage.blob.core.windows.net` — имя узла учетной записи хранения;
- `*.powershellgallery.com` — веб-сайт;
- `go.microsoft.com` — служба перенаправления.
- `onegetcdn.azureedge.net` — начальная загрузка поставщика NuGet в `PowerShellGet/PackageManagement`.

> [!NOTE]
> Если возникнет сбой служб коллекции PowerShell, командлеты, которые взаимодействуют с коллекцией PowerShell, могут привести к сбою с непредвиденными ошибками. Сведения о текущем состоянии коллекции PowerShell см. на странице [Состояние коллекции PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) на сайте GitHub.
