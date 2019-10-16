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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360673"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Изменение пути установки PSModulePath

Переменная среды `PSModulePath` сохраняет пути к расположениям модулей, установленных на диске. Windows PowerShell использует эту переменную для поиска модулей, когда пользователь не указал полный путь к модулю. Пути в этой переменной ищутся в том порядке, в котором они отображаются.

При запуске Windows PowerShell `PSModulePath` создается как системная переменная среды со следующим значением по умолчанию: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`.

## <a name="to-view-the-psmodulepath-variable"></a>Просмотр переменной PSModulePath

Чтобы просмотреть пути, указанные в переменной `PSModulePath`, введите следующую команду:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Добавление расположений в переменную PSModulePath

Чтобы добавить пути к этой переменной, используйте один из следующих методов.

- Чтобы добавить временное значение, доступное только для текущего сеанса, выполните в командной строке следующую команду:

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- Чтобы добавить постоянное значение, доступное при каждом открытии сеанса, добавьте следующую команду в профиль Windows PowerShell:

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) в библиотеке Microsoft TechNet.

- Чтобы добавить постоянную переменную в реестр, создайте новую переменную среды пользователя с именем `PSModulePath` с помощью редактора переменных среды в диалоговом окне " **Свойства системы** ".

- Чтобы добавить постоянную переменную с помощью скрипта, используйте метод **SetEnvironmentVariable** класса Environment. Например, следующий скрипт добавляет путь "C:\Program Филес\фабрикам\модуле" к значению переменной среды PSModulePath для компьютера. Чтобы добавить путь к переменной среды пользователя PSModulePath, задайте для целевого объекта значение "User".

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Удаление расположений из PSModulePath

Вы можете удалить пути из переменной с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` удалит путь **к:\модулепас** из текущего сеанса.

## <a name="see-also"></a>См. также:

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
