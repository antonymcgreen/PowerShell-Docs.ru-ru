---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 46a278b83edb9d8e3d75b0874603710d416be3b5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680119"
---
# <a name="import-dscresource-keyword-supports--moduleversion-parameter"></a>Ключевое слово Import-DscResource поддерживает параметр -moduleversion

Мы добавили в динамическое ключевое слово `Import-DscResource` новый параметр, доступный при создании конфигураций DSC. Авторы конфигурации теперь могут указать, из какой именно версии модуля следует загружать ресурсы DSC. Новый синтаксис ключевого слова имеет следующий вид.

```powershell
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName(s)>] [-ModuleVersion <ModuleVersion>]
```

* **Name:** имена одного или нескольких импортируемых ресурсов.
* **Имя ModuleName**: имена или объекты ModuleSpecification одного или нескольких импортируемых модулей.
* **ModuleVersion**: версия импортируемого модуля. При использовании значение ModuleName должно представлять по имени всего один модуль.

В интегрированной среде сценариев Windows PowerShell оно отображается с IntelliSense:

![](../images/Import-DscResource-Modversion.jpg)

**Примечание**. Параметр `–ModuleVersion` можно использовать только вместе с параметром `–ModuleName`. Его нельзя использовать с именами ресурсов, используя только параметр `–Name`.

До этого единственный способ для указания версии модуля при загрузке ресурсов DSC заключался в использовании объекта спецификации модуля, например `–ModuleName @{ModuleName="UserConfigProvider";ModuleVersion="3.0"}`.
