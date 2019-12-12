---
ms.date: 09/11/2018
contributor: JKeithB
keywords: gallery,powershell,psgallery
title: Скачивание пакета вручную
ms.openlocfilehash: c0a96e866dfd27f9b2170ea540ec6dd0c67701fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71327895"
---
# <a name="manual-package-download"></a>Скачивание пакета вручную

В коллекции Powershell поддерживается прямое скачивание пакета с веб-сайта без использования командлетов PowerShellGet. Любой пакет можно скачать в формате NuGet (файла с расширением `.nupkg`), который можно копировать во внутренний репозиторий.

> [!NOTE]
> Скачивание пакета вручную **не** является заменой использования командлета `Install-Module`.
> При скачивании пакета не выполняется установка модуля или сценария. В скачанном пакете NuGet нет зависимостей. Следующие инструкции приводятся только в информационных целях.

## <a name="using-manual-download-to-acquire-a-package"></a>Получение пакета с помощью скачивания вручную

На каждой странице находится ссылка для скачивания вручную, как показано ниже.

![Скачивание вручную](../../Images/packagedisplaypagewithpseditions.png)

Чтобы скачать пакет вручную, щелкните ссылку **Скачать необработанный NUPKG-файл**. Копия пакета копируется в папку загрузки с именем `<name>.<version>.nupkg`.

Пакет NuGet — это ZIP-архив с дополнительными файлами, содержащими сведения о содержимом пакета. Некоторые браузеры, например Internet Explorer, автоматически заменяют расширение `.nupkg` на `.zip`. Чтобы развернуть пакет, при необходимости переименуйте файл `.nupkg` в `.zip`, затем извлеките его содержимое в локальную папку.

Файл пакета NuGet содержит следующие **характерные для NuGet элементы**, которые не являются частью исходного упакованного кода:

- Папка `_rels` содержит файл `.rels` со списком зависимостей.
- Папка `package` содержит характерные для NuGet данные.
- Файл `[Content_Types].xml` описывает работу расширений, например PowerShellGet, с помощью NuGet.
- Файл `<name>.nuspec` содержит основной объем метаданных.

## <a name="installing-powershell-modules-from-a-nuget-package"></a>Установка модулей PowerShell из пакета NuGet

> [!NOTE]
> Результат выполнения этих инструкций **отличается** от результата запуска командлета `Install-Module`. Эти инструкции отвечают минимальным требованиям. Они не предназначены для использования в качестве замены `Install-Module`.
> Некоторые шаги, выполняемые командлетом `Install-Module`, не указаны.

Проще всего удалить характерные для NuGet элементы из папки. При удалении элементов код PowerShell, созданный автором пакета, остается без изменений.
Список элементов, относящихся к NuGet, см. в разделе о [скачивании пакета вручную](#using-manual-download-to-acquire-a-package).

Процесс состоит из следующих этапов.

1. Извлечь содержимое пакета NuGet в локальную папку.
2. Удалить характерные для NuGet элементы из папки.
3. Переименовать папку. По умолчанию используется имя папки `<name>.<version>`. Номер версии может содержать `-prerelease`, если модуль помечен как предварительная версия. Задать для папки имя модуля. Например, `azurerm.storage.5.0.4-preview` преобразуется в `azurerm.storage`.
4. Скопируйте папку в одну из папок в `$env:PSModulePath value`. `$env:PSModulePath` — это набор разделенных точками с запятой путей, в которых оболочка PowerShell должна искать модули.

> [!IMPORTANT]
> При скачивании вручную не включаются зависимости, необходимые для модуля. Если у пакета есть зависимости, они должны быть установлены в системе для правильной работы этого модуля. В коллекции PowerShell отображаются все зависимости, необходимые для пакета.

## <a name="installing-powershell-scripts-from-a-nuget-package"></a>Установка сценариев PowerShell из пакета NuGet

> [!NOTE]
> Результат выполнения этих инструкций **отличается** от результата запуска командлета `Install-Script`. Эти инструкции отвечают минимальным требованиям. Они не предназначены для использования в качестве замены `Install-Script`.

Самым простым способом является извлечение пакета NuGet и использование сценария напрямую.

Процесс состоит из следующих этапов.

1. Извлечь содержимое пакета NuGet в локальную папку.
2. Файл `.PS1` в папке можно использовать прямо из этого расположения.
3. Можно удалить характерные для NuGet элементы в папке.

Список элементов, относящихся к NuGet, см. в разделе о [скачивании пакета вручную](#using-manual-download-to-acquire-a-package).

> [!IMPORTANT]
> При скачивании вручную не включаются зависимости, необходимые для модуля. Если у пакета есть зависимости, они должны быть установлены в системе для правильной работы этого модуля. В коллекции PowerShell отображаются все зависимости, необходимые для пакета.