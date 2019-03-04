---
title: 'Создание обновляемой справки: Пошаговые | Документация Майкрософт'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: fbc77cc0fafce93d239da1c459d4b761b21ef3cb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860320"
---
# <a name="updatable-help-authoring-step-by-step"></a>Создание обновляемой справки: пошаговые инструкции

Этот документ перечислены этапы разработки, обновляемую справку.

## <a name="authoring-updatable-help-step-by-step"></a>Создание обновляемой справки: пошаговые инструкции

Обновляемой справки предназначена для конечных пользователей, но он также обеспечивает значительные преимущества для авторы модулей и записи справки, включая возможность добавления содержимого, исправления ошибок, обеспечивают несколько языков и региональных параметров пользовательского интерфейса и отвечать на комментарии пользователей и запросов, время после модуль был доставлен. В этом разделе объясняется, как вы пакет и файлах справки передачи таким образом, чтобы пользователи могут загрузить и установить их с помощью [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлетов.

Ниже приведены общие сведения о поддержке обновляемой справки в процессе.

### <a name="step-1-find-an-internet-site-for-your-help-files"></a>Шаг 1. Найти сайт в Интернете для файлы справки

Создание обновляемой справки первым делом для поиска расположения в Интернете для вашего модуля файлы справки. На самом деле можно использовать два разных расположениях. Вы можете сохранить файл сведений о вашего модуля справке (HelpInfo XML - описано ниже) одного расположения в Интернете и CAB-файлы содержимого справки в другом расположении в Интернете. Все файлы с содержимым CAB-файла с справки для модуля должны находиться в одном расположении. CAB-файлы справки для содержимого для различных модулей можно разместить в том же расположении.

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a>Шаг 2. Добавить ключ HelpInfoURI в манифесте модуля

Добавить **HelpInfoURI** ключа в манифест модуля. Значение ключа является универсальный код ресурса (URI) расположения файла сведения HelpInfo XML для модуля. Для обеспечения безопасности адрес должен начинаться с «http» или «https». URI должен указывать расположение Internet, но не должен включать имя файла HelpInfo XML.

Например:

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'http://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a>Шаг 3. Создайте файл HelpInfo XML

HelpInfo XML-файле информацию содержит URI расположения в Интернете файлы справки и номера версий новейшие файлы справки для модуля в каждый поддерживаемый язык и региональные параметры пользовательского интерфейса. Каждый модуль Windows PowerShell имеет один XML-файл HelpInfo. При обновлении файлы справки, можно изменить или заменить файл HelpInfo XML; не следует добавлять другой. Дополнительные сведения см. в разделе [способ создания XML-файл HelpInfo](./how-to-create-a-helpinfo-xml-file.md).

### <a name="step-4-sign-your-help-files"></a>Шаг 4. Подпись файлов справки

Цифровые подписи не являются обязательными, но они являются лучшим рекомендацию всякий раз, когда предоставляется доступ к файлам.

### <a name="step-5-create-cab-files"></a>Шаг 5. Создание CAB-файлы

Используйте средство, которое создает CAB-файлы, такие как MakeCab.exe для создания. CAB-файл, содержащий файлы справки для модуля. Создайте отдельный CAB-файл, файлы справки для каждого поддерживаемого языка и региональных параметров пользовательского интерфейса. Дополнительные сведения см. в разделе [как подготовка обновляемых файлов справки CAB](./how-to-prepare-updatable-help-cab-files.md).

### <a name="step-6-upload-your-files"></a>Шаг 6. Передача файлов

Чтобы опубликовать новые или обновленные файлы справки, загрузить CAB-файлы в расположения в Интернете, задаваемый **HelpContentUri** в файле HelpInfo XML. Отправьте XML-файл HelpInfo для расположения в Интернете, указанный по значению **HelpInfoUri** ключа в манифесте модуля.