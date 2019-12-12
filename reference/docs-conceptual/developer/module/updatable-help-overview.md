---
title: Обзор обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: 3f7388a9-9fa8-42bc-b294-538c9a01e30a
caps.latest.revision: 12
ms.openlocfilehash: f2dfb9642ba2dde38124142b659b425bbbb00f37
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366963"
---
# <a name="updatable-help-overview"></a>Общие сведения об обновляемой справке

Этот документ содержит основные сведения о проектировании и работе функции обновляемой справки Windows PowerShell. Он предназначен для авторов модулей и других пользователей, которые предоставляют пользователям разделы справки по Windows PowerShell.

## <a name="introduction"></a>Введение

Разделы справки по Windows PowerShell являются неотъемлемой частью интерфейса Windows PowerShell. Как и модули Windows PowerShell, разделы справки постоянно обновляются и улучшаются авторами и вкладами сообщества пользователей Windows PowerShell.

Функция *обновляемой справки* , появившаяся в Windows PowerShell 3,0, гарантирует, что пользователи имеют новейшие версии разделов справки в командной строке, даже встроенные команды Windows PowerShell, не загружая новые модули или запуская центр обновления Windows. Обновляемая Справка делает обновление простым, предоставляя командлеты, которые загружают последние версии разделов справки из Интернета и устанавливают их в нужные подкаталоги на локальном компьютере пользователя. Даже пользователи, находящиеся за брандмауэрами, могут использовать новые командлеты для получения обновленной справки из внутренней общей папки.

Обновляемая Справка полностью поддерживается всеми модулями Windows PowerShell в Windows® 8 и Windows Server® 2012, а ее функции доступны всем авторам модулей Windows PowerShell. Обновляемая Справка поддерживает только файлы справки на основе XML. Он не поддерживает справку на основе комментариев.

Обновляемая Справка содержит следующие функции.

- Командлет [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) , который определяет, имеют ли пользователи самые новые файлы справки для модуля и, если нет, загружает новейшие файлы справки из Интернета, распаковать их и установит в соответствующих подкаталогах модуля на компьютере пользователя.
  Пользователи могут использовать командлет [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) для немедленного просмотра недавно установленных разделов справки.
  Им не нужно перезапускать PowerShell.

- Командлет [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) , который скачивает новейшие файлы справки из Интернета и сохраняет их в каталоге файловой системы. Пользователи могут использовать командлет `Update-Help` для получения файлов справки из каталога файловой системы, а также распаковать и установить их в подкаталогах модуля на компьютере пользователя. Командлет `Save-Help` предназначен для пользователей с ограниченным доступом к Интернету и для предприятий, предпочитающих ограничить доступ к Интернету.

- **Справка по модулю**. Файлы справки для модуля управляются и доставляются как единое целое, поэтому пользователи могут получить все файлы справки для используемых модулей. Обновляемая Справка поддерживается только для модулей, а не для оснасток Windows PowerShell.

- **Поддержка версий**. Обновляемая Справка использует стандартное 4-Позиционирование (N1. N2. N3. N4) номера версий. Обновляемая Справка скачивает файлы справки, когда номер версии файлов справки на компьютере пользователя (или в каталоге `Save-Help`) ниже номера версии файлов справки в Интернете.

- **Поддержка нескольких языков**. Обновляемая Справка поддерживает файлы справки по модулям в нескольких культурах пользовательского интерфейса. Обновляемые имена файлов справки включают стандартные коды языков, такие как "en-US" и "ja-JP", а командлеты `Update-Help` и `Save-Help` помещают файлы справки в подкаталоги для конкретного языка каталога модуля.

- **Автоматически созданная Справка**. Командлет [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) отображает основную справку для команд, не имеющих файлов справки. Автоматически созданная Справка содержит синтаксис команд и псевдонимы, а также инструкции по использованию интерактивной справки и обновляемой справки.

- **Улучшенная Справка в Интернете**. Для простого доступа к справке в сети больше не требуется файлов справки. Параметр **Online** командлета `Get-Help` теперь получает URL-адрес раздела справки в Интернете из значения свойства **HelpUri** любой команды, если не удается найти URL-адрес справки в Интернете в файле справки. Свойство **HelpUri** можно заполнить путем добавления атрибута **HelpUri** в код командлетов, функций и команд CIM или с помощью **. Ссылка** на директиву справки на основе комментария в рабочих процессах и скриптах.

  Чтобы обеспечить обновление файлов справки, модули Windows PowerShell в Windows 8 и Windows Server vNext не поставляются с файлами справки. Пользователи могут использовать обновляемую справку для установки файлов справки и их обновления. Авторы других модулей могут включать файлы справки в модули или опускать их. Поддержка обновляемой справки является необязательной, но рекомендуется.