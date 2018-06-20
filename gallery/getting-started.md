---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Приступая к работе с коллекцией PowerShell
ms.openlocfilehash: 83974698152e75efac66ea725a9c220486676d6f
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190168"
---
# <a name="get-started-with-the-powershell-gallery"></a>Приступая к работе с коллекцией PowerShell

Для скачивания элементов из коллекции PowerShell требуется модуль [PowerShellGet](/powershell/module/powershellget). Модуль PowerShellGet можно найти в перечисленных ниже источниках. Входить в систему для скачивания элементов из коллекции PowerShell необязательно.

## <a name="discovering-items-from-the-powershell-gallery"></a>Обнаружение элементов в коллекции PowerShell

Найти элементы в коллекции PowerShell можно при помощи элемента управления **Поиск** на сайте или просмотрев страницы "Модули" и "Скрипты". Найти элементы в коллекции PowerShell можно также при помощи командлетов [Find-Module][] и [Find-Script][] (в зависимости от типа элемента) с параметром `-Repository PSGallery`.

Для фильтрации результатов поиска в коллекции используются следующие параметры:

- Name
- AllVersions
- MinimumVersion
- RequiredVersion
- Tag
- Includes
- DscResource
- RoleCapability
- Команда
- Фильтр

Если вас интересуют только определенные ресурсы DSC в коллекции, выполните командлет [Find-DscResource]. Командлет Find-DscResource возвращает сведения о ресурсах DSC, содержащихся в коллекции.
Поскольку ресурсы DSC всегда являются частью модуля, вам по-прежнему потребуется выполнить командлет [Install-Module][], чтобы установить их.

## <a name="learning-about-items-in-the-powershell-gallery"></a>Изучение элементов в коллекции PowerShell

Когда вы нашли элемент, который вас интересует, о нем можно узнать больше. Для этого можно изучить страницу конкретного элемента в коллекции. На ней представлены все метаданные, переданные вместе с элементом. Эти метаданные предоставляются автором элемента и не проверяются корпорацией Майкрософт. Владелец элемента тесно связан с учетной записью в коллекции, используемой для публикации элемента, поэтому ориентироваться на нее — более надежно, чем на информацию в поле "Автор".

Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.

При использовании командлетов [Find-Module][] или [Find-Script][] эти данные можно доступны в возвращенном объекте PSGetModuleInfo. Например, при выполнении `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` возвращаются сведения о модуле PSReadLine, содержащемся в коллекции.

## <a name="downloading-items-from-the-powershell-gallery"></a>Скачивание элементов из коллекции PowerShell

При скачивании элементов из коллекции PowerShell рекомендуется использовать следующий процесс.

### <a name="inspect"></a>Изучение

Чтобы скачать элемент из коллекции для изучения, выполните командлет [Save-Module][] или [Save-Script][] в зависимости от типа элемента. Так вы сможете сохранить элемент локально без установки и проверить его содержимое. Не забудьте удалить элемент, сохраненный вручную.

Некоторые из этих элементов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.
Корпорация Майкрософт рекомендует ознакомиться с содержимым и кодом элементов в этой коллекции перед их установкой.

Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.

### <a name="install"></a>Установка

Чтобы установить элемент из коллекции для использования, выполните командлет [Install-Module][] или [Install-Script][] в зависимости от типа элемента.

Командлет [Install-Module][] устанавливает модуль в `$env:ProgramFiles\WindowsPowerShell\Modules` по умолчанию.
Для выполнения этой операции необходима учетная запись администратора. При добавлении параметра `-Scope CurrentUser` модуль будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Modules`.

Командлет [Install-Script][] по умолчанию устанавливает скрипт в каталог `$env:ProgramFiles\WindowsPowerShell\Scripts`.
Для выполнения этой операции необходима учетная запись администратора. При добавлении параметра `-Scope CurrentUser` скрипт будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts`.

По умолчанию командлеты [Install-Module][] and [Install-Script][] устанавливают последнюю версию элемента.
Чтобы установить более раннюю версию элемента, добавьте параметр `-RequiredVersion`.

### <a name="deploy"></a>Развертывание

Чтобы развернуть элемент из коллекции PowerShell в службе автоматизации Azure, нажмите кнопку **Развернуть в службе автоматизации Azure** на странице подробностей об элементе. После этого вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure. Обратите внимание, что развертывание элементов с зависимостями приводит к развертыванию всех зависимостей в службе автоматизации Azure. Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег **AzureAutomationNotSupported** в метаданные элемента.

Дополнительные сведения о службе автоматизации Azure см. в [соответствующей](/azure/automation) документации.

## <a name="updating-items-from-the-powershell-gallery"></a>Обновление элементов из коллекции PowerShell

Чтобы обновить элементы, установленные из коллекции PowerShell, выполните командлет [Update-Module][] или [Update-Script][]. При запуске без дополнительных параметров [Update-Module][] пытается обновить каждый модуль, установленный командлетом [Install-Module][]. Чтобы выборочно обновить модули, добавьте параметр `-Name`.

Аналогично при запуске без дополнительных параметров [Update-Script][] пытается обновить каждый сценарий, установленный командлетом [Install-Script][]. Чтобы выборочно обновить скрипты, добавьте параметр `-Name`.

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a>Перечисление элементов, установленных из коллекции PowerShell

Чтобы узнать, какие модули вы установили из коллекции PowerShell, выполните командлет [Get-InstalledModule][]. Эта команда перечисляет все модули в системе, установленные непосредственно из коллекции PowerShell.

Аналогично, чтобы узнать, какие скрипты были установлены из коллекции PowerShell, выполните командлет [Get-InstalledScript][]. Эта команда перечисляет все скрипты в системе, установленные непосредственно из коллекции PowerShell.

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script