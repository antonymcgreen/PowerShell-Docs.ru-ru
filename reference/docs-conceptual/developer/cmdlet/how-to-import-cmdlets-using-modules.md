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
ms.openlocfilehash: 2f145795a57c988da0cb4ed294142aa141c53cae
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364463"
---
# <a name="how-to-import-cmdlets-using-modules"></a>Импорт командлетов с помощью модулей

В этой статье описывается, как импортировать командлеты в сеанс PowerShell с помощью двоичного модуля.

> [!NOTE]
> Членами модулей могут быть командлеты, поставщики, функции, переменные, псевдонимы и многое другое. Оснастки могут содержать только командлеты и поставщики.

## <a name="how-to-load-cmdlets-using-a-module"></a>Как загружать командлеты с помощью модуля

1. Создайте папку модуля, имя которой совпадает с именем файла сборки, в котором реализуются командлеты. В этой процедуре папка Module создается в папке `system32` Windows.

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. Убедитесь, что переменная среды `PSModulePath` содержит путь к новой папке модуля. По умолчанию системная папка уже добавлена в переменную среды `PSModulePath`. Чтобы просмотреть `PSModulePath`, введите: `$env:PSModulePath`.

1. Скопируйте сборку командлета в папку Module.

1. Добавьте файл манифеста модуля (`.psd1`) в корневую папку модуля. PowerShell использует манифест модуля для импорта модуля. Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md).

1. Выполните следующую команду, чтобы добавить командлеты в сеанс:

   `Import-Module [Module_Name]`

   Эту процедуру можно использовать для проверки командлетов. Он добавляет все командлеты в сборку в сеанс. Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>См. также статью

[Написание манифеста модуля PowerShell](../module/how-to-write-a-powershell-module-manifest.md)

[Импорт модуля PowerShell](../module/importing-a-powershell-module.md)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Установка модулей](../module/installing-a-powershell-module.md)

[Изменение пути установки PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
