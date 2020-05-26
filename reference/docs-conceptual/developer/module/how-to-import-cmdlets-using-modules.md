---
title: Импорт командлетов с помощью модулей | Документация Майкрософт
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 840c5bc92d718ec4e54d864dc5e012cd33f83905
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811323"
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

## <a name="see-also"></a>См. также статью

[Как написать манифест модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md)

[Импорт модуля PowerShell](../module/importing-a-powershell-module.md)

[Импорт-модуль](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Установка модулей](../module/installing-a-powershell-module.md)

[Изменение пути установки PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Запись командлета Windows PowerShell](../cmdlet/cmdlet-overview.md)
