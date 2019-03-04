---
title: Изменение пути установки PSModulePath | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855570"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Изменение пути установки PSModulePath

`PSModulePath` Переменной среды сохраняет пути для расположения модулей, установленных на диске. Windows PowerShell использует эту переменную для поиска модулей, когда пользователь не указывает полный путь к модулю. Поиск путей в этой переменной выполняется в порядке, в котором они появляются.

При запуске Windows PowerShell, `PSModulePath` создается как системную переменную среды со следующим значением по умолчанию: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.

## <a name="to-view-the-psmodulepath-variable"></a>Чтобы просмотреть переменной PSModulePath

Чтобы просмотреть пути, указанные в `PSModulePath` переменной, введите следующую команду:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Чтобы добавить расположения в переменную PSModulePath

Чтобы добавить пути к этой переменной, используйте один из следующих методов:

- Чтобы добавить временное значение, которое доступно только для текущего сеанса, выполните следующую команду в командной строке:

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- Чтобы добавить постоянное значение, которое доступно каждый раз, когда открывается сеанс, добавьте следующую команду в профиль Windows PowerShell:

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) в библиотеке Microsoft TechNet.

- Чтобы добавить переменную постоянных в реестр, создайте новую переменную среды пользователя с именем `PSModulePath` с помощью редактора переменные среды в **системные свойства** диалоговое окно.

- Чтобы добавить постоянный переменной с помощью сценария, используйте **SetEnvironmentVariable** метод к классу среды. Например следующий сценарий добавляет «C:\Program Files\Fabrikam\Module путь к значению переменной среды PSModulePath для компьютера. Чтобы добавить путь в переменной среды PSModulePath пользователя, задайте целевой объект «User».

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Для удаления расположений из PSModulePath

Можно удалить пути из переменной, с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` приведет к удалению **c:\ModulePath** пути из текущего сеанса.

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
