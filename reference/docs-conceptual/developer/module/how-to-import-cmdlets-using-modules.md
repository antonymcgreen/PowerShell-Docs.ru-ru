---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.date: 08/28/2019
ms.openlocfilehash: fa8d629c14b06e3f9e9d6151cf09aa6b4acce358
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779375"
---
# <a name="how-to-import-cmdlets-using-modules"></a>Импорт командлетов с помощью модулей

В этой статье описывается, как импортировать командлеты в сеанс PowerShell с помощью двоичного модуля.

> [!NOTE]
> Членами модулей могут быть командлеты, поставщики, функции, переменные, псевдонимы и многое другое. Оснастки могут содержать только командлеты и поставщики.

## <a name="how-to-load-cmdlets-using-a-module"></a>Как загружать командлеты с помощью модуля

1. Создайте папку модуля, имя которой совпадает с именем файла сборки, в котором реализуются командлеты. В этой процедуре папка Module создается в `system32` папке Windows.

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. Убедитесь, что `PSModulePath` переменная среды содержит путь к новой папке модуля. По умолчанию системная папка уже добавлена в `PSModulePath` переменную среды. Чтобы просмотреть `PSModulePath` , введите: `$env:PSModulePath` .

1. Скопируйте сборку командлета в папку Module.

1. Добавьте файл манифеста модуля ( `.psd1` ) в корневую папку модуля. PowerShell использует манифест модуля для импорта модуля. Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md).

1. Выполните следующую команду, чтобы добавить командлеты в сеанс:

   `Import-Module [Module_Name]`

   Эту процедуру можно использовать для проверки командлетов. Он добавляет все командлеты в сборку в сеанс. Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>См. также

[Как написать манифест модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md)

[Импорт модуля PowerShell](../module/importing-a-powershell-module.md)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Установка модулей](../module/installing-a-powershell-module.md)

[Изменение пути установки PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Запись командлета Windows PowerShell](../cmdlet/cmdlet-overview.md)
