---
description: PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 5b4b42dfce03831da5cc317276e78e0777ff73d6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232570"
---
# <a name="about-packagemanagement"></a>Сведения о PackageManagement

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Функция PackageManagement появилась в Windows PowerShell 5,0.

PackageManagement — это единый интерфейс для систем управления пакетами программного обеспечения; Командлеты PackageManagement можно использовать для выполнения задач обнаружения программного обеспечения, установки и инвентаризации (СДИИ). Независимо от базовой технологии установки можно выполнять общие командлеты в модуле PackageManagement для поиска, установки и удаления пакетов. добавлять, удалять и запрашивать репозитории пакетов; и запускают запросы на компьютере, чтобы определить, какие пакеты программного обеспечения установлены.

PackageManagement поддерживает гибкую модель подключаемых модулей, которая обеспечивает поддержку других систем управления пакетами программного обеспечения.

Модуль PackageManagement входит в состав Windows PowerShell 5,0 и более поздних выпусков PowerShell и работает на трех уровнях структуры управления пакетами: поставщиками пакетов, источниками пакетов и самими пакетами. Давайте определим некоторые термины:

- Диспетчер пакетов: система управления пакетами программного обеспечения. В терминах PackageManagement это поставщик пакетов.
- Поставщик пакетов: термин PackageManagement для диспетчера пакетов. Примерами могут быть установщик Windows, шоколад и другие.
- Источник пакета: URL-адрес, локальная папка или общая сетевая папка, в которой поставщики пакетов настраиваются для использования в качестве репозитория.
- Package — это программное обеспечение, которое управляется поставщиком пакетов и хранится в определенном источнике пакета.

Модуль PackageManagement содержит следующие командлеты. Дополнительные сведения см. в справке [PackageManagement](/powershell/module/packagemanagement) .

- `Get-PackageProvider`: Возвращает список поставщиков пакетов, подключенных к PackageManagement.
- `Get-PackageSource`: Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.
- `Register-PackageSource`: Добавляет источник пакета для указанного поставщика пакетов.
- `Set-PackageSource`: Задает свойства для существующего источника пакета.
- `Unregister-PackageSource`: Удаляет зарегистрированный источник пакета.
- `Get-Package`: Возвращает список установленных программных пакетов.
- `Find-Package`: Поиск пакетов программного обеспечения в доступных источниках пакетов.
- `Install-Package`: Устанавливает один или несколько пакетов программного обеспечения.
- `Save-Package`: Сохраняет пакеты на локальном компьютере, не устанавливая их.
- `Uninstall-Package`: Удаляет один или несколько пакетов программного обеспечения.

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a>Начальная загрузка поставщика пакетов и параметры динамических командлетов

По умолчанию PackageManagement поставляется с основным поставщиком начальной загрузки. Вы можете установить дополнительные поставщики пакетов по мере необходимости, заполнив начальную загрузку поставщиков. Это значит, что отвечает на запрос на автоматическую установку поставщика из веб-службы. Поставщик пакетов можно указать с помощью любого командлета PackageManagement; Если указанный поставщик недоступен, PackageManagement предлагает выполнить начальную загрузку (или автоматическую установку) поставщика. В следующих примерах, если поставщик шоколада еще не установлен, начальная загрузка PackageManagement устанавливает поставщик.

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

Если поставщик шоколад еще не установлен, при выполнении предыдущей команды будет предложено установить его.

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

Если поставщик шоколад еще не установлен, при выполнении предыдущей команды поставщик устанавливается; Но поскольку в команду был добавлен параметр Форцебутстрап, вам не будет предложено установить его. как поставщик, так и пакет устанавливаются автоматически.

При попытке установить пакет, если у вас еще не установлен поставщик поддержки и вы не добавили в команду параметр Форцебутстрап, PackageManagement предложит установить поставщик.

При указании поставщика пакетов в команде PackageManagement могут быть доступны динамические параметры, характерные для данного поставщика пакетов. При запуске Get-Help для конкретного командлета PackageManagement возвращается список наборов параметров, объединяющий динамические параметры для доступных поставщиков пакетов в отдельных наборах параметров.

Дополнительные сведения о проекте PackageManagement

Дополнительные сведения о проекте PackageManagement Open Development, включая создание поставщика пакетов PackageManagement, см. в проекте PackageManagement на сайте GitHub по адресу https://oneget.org .

## <a name="see-also"></a>СМ. ТАКЖЕ

[Get-PackageProvider](xref:PackageManagement.Get-PackageProvider)

[Get-PackageSource](xref:PackageManagement.Get-PackageSource)

[Register-PackageSource](xref:PackageManagement.Register-PackageSource)

[Set-PackageSource](xref:PackageManagement.Set-PackageSource)

[Unregister-PackageSource](xref:PackageManagement.Unregister-PackageSource)

[Get-Package](xref:PackageManagement.Get-Package)

[Find-Package](xref:PackageManagement.Find-Package)

[Install-Package](xref:PackageManagement.Install-Package)

[Save-Package](xref:PackageManagement.Save-Package)

[Uninstall-Package](xref:PackageManagement.Uninstall-Package)
