---
title: Создание справки на основе XML с помощью PlatyPS
description: Использование PlatyPS — это быстрый и эффективный способ создания справки на основе XML.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972598"
---
# <a name="create-xml-based-help-using-platyps"></a>Создание справки на основе XML с помощью PlatyPS

При создании модуля PowerShell всегда рекомендуется включать подробную справку по созданным командлетам. Если командлеты реализованы в компилированном коде, необходимо использовать справку на основе XML. Этот формат XML известен как язык разметки Microsoft Assistance (MAML).

В устаревшей документации по пакету SDK PowerShell содержатся сведения о создании справки по командлетам PowerShell, упакованным в модули. Однако PowerShell не предоставляет средства для создания справки на основе XML. В документации по пакету SDK описывается структура справки MAML, но вы должны сами создать сложное содержимое MAML с множеством вложенных разделов.

В этом вам поможет модуль [PlatyPS][].

## <a name="what-is-platyps"></a>Что такое PlatyPS?

PlatyPS — это инструмент [с открытым кодом][platyps-repo], который был придуман в рамках _хакатона_, чтобы упростить создание и обслуживание MAML. PlatyPS документирует синтаксис наборов параметров и отдельных параметров для каждого командлета в модуле. PlatyPS создает структурированные файлы [Markdown][], содержащие сведения о синтаксисе. Он не может создавать описания или предоставлять примеры,

зато создает заполнители для описаний и примеров. После добавления необходимой информации PlatyPS компилирует файлы Markdown в файлы MAML. Справочная система PowerShell также допускает файлы справки в виде обычного текста (разделы общих сведений). В PlatyPS есть командлет для создания структурированного шаблона Markdown для нового файла _общих сведений_, но эти файлы `about_*.help.txt` необходимо обслуживать вручную.

В модуль можно включить файлы справки MAML и текстовые файлы. Можно также использовать PlatyPS для компиляции файлов справки в пакет CAB, который можно разместить для реализации функции обновления.

## <a name="get-started-using-platyps"></a>Начало работы с PlatyPS

Сначала необходимо установить PlatyPS из коллекции PowerShell.

```powershell
Install-Module platyps -Force
Import-Module platyps
```

В следующей блок-схеме описывается процесс создания или обновления справочного содержимого PowerShell.

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="Рабочий процесс создания справки на основе XML с помощью PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a>Создание содержимого Markdown для модуля PowerShell

1. Импортируйте новый модуль в сеанс. Повторите этот шаг для каждого модуля, который необходимо задокументировать.

   Выполните следующую команду для импорта модулей.

   ```powershell
   Import-Module <your module name>
   ```

1. Используйте PlatyPS для создания файлов Markdown для страницы модуля и всех связанных командлетов в модуле. Повторите этот шаг для каждого модуля, который необходимо задокументировать.

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   Если папка выходных данных не существует, `New-MarkdownHelp` создаст ее. В этом примере `New-MarkdownHelp` создает файл Markdown для каждого командлета в модуле. Он также создает _страницу модуля_ в файле с именем `<ModuleName>.md`. Эта страница модуля включает список командлетов, содержащихся в модуле, и заполнители для **краткого описания**. Метаданные на странице модуля берутся из манифеста модуля и используются PlatyPS для создания XML-файла HelpInfo (как описано [ниже](#creating-an-updateable-help-package)).

   `New-MarkdownAboutHelp` создает новый файл _общих сведений_ с именем `about_topic_name.md`.

   Дополнительные сведения см. в статьях [New-MarkdownHelp][] и [New-MarkdownAboutHelp][].

### <a name="update-existing-markdown-content-when-the-module-changes"></a>Обновление существующего содержимого Markdown при изменении модуля

PlatyPS также может обновлять существующие файлы Markdown для модуля. Используйте этот шаг, чтобы обновить существующие модули с новыми командлетами, новыми параметрами или измененными параметрами.

1. Импортируйте новый модуль в сеанс. Повторите этот шаг для каждого модуля, который необходимо задокументировать.

   Выполните следующую команду для импорта модулей.

   ```powershell
   Import-Module <your module name>
   ```

1. Используйте PlatyPS для обновления файлов Markdown для целевой страницы модуля и всех связанных командлетов в модуле. Повторите этот шаг для каждого модуля, который необходимо задокументировать.

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   `Update-MarkdownHelpModule` обновляет командлет и файлы Markdown модуля в указанной папке.
   Файлы `about_*.md` не обновляются. Файл модуля (`ModuleName.md`) получает новый текст **краткого описания**, добавленный в файлы командлетов. Обновления файлов командлетов включают следующие изменения.

   - Наборы новых параметров
   - Новые параметры
   - Обновленные метаданные параметра
   - Обновленные сведения о типах входных и выходных данных

   Дополнительные сведения см. в разделе [Update-MarkdownHelpModule][].

## <a name="edit-the-new-or-updated-markdown-files"></a>Изменение новых или обновленных файлов Markdown

PlatyPS документирует синтаксис наборов параметров и отдельных параметров. Он не может создавать описания или предоставлять примеры, а конкретные области, в которых требуется содержимое, содержатся в фигурных скобках. Пример: `{{ Fill in the Description }}`

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Шаблон Markdown, отображающий заполнители в VS Code":::

Необходимо добавить краткое описание, описание командлета, описания для каждого параметра и хотя бы один пример.

Подробные сведения о записи содержимого PowerShell см. в следующих статьях.

- [Руководство по стилю для PowerShell](/powershell/scripting/community/contributing/powershell-style-guide)
- [Изменение справочных статей](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> В PlatyPS существует определенная схема, которая используется для ссылки на командлет. Эта схема допускает только определенные блоки Markdown в определенных разделах документа. Если содержимое размещено в неправильном расположении, шаг сборки PlatyPS завершается ошибкой. Дополнительные сведения см. в документации по [схеме][] в репозитории PlatyPS. Полный пример справки по командлетам с правильным форматом см. в разделе [Get-Item][].

Предоставив необходимое содержимое для каждого командлета, необходимо обновить целевую страницу модуля. Убедитесь, что модуль имеет правильные значения `Module Guid` и `Download Help Link` в метаданных YAML файла `<module-name>.md`. Добавьте отсутствующие метаданные.

Кроме того, вы можете заметить, что у некоторых командлетов не хватает **краткого описания** (_синопсиса_). Следующая команда обновляет целевую страницу модуля, указав текст **краткого описания**. Откройте целевую страницу модуля, чтобы проверить описания.

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

Теперь, когда все содержимое введено, вы можете создать файлы справки MAML, отображаемые `Get-Help` в консоли PowerShell.

## <a name="create-the-external-help-files"></a>Создание внешних файлов справки

На этом шаге создаются файлы справки MAML, которые отображаются `Get-Help` в консоли PowerShell.

Чтобы создать файлы MAML, выполните следующую команду.

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

`New-ExternalHelp` преобразует все файлы Markdown командлета в один файл MAML (или несколько). Файлы с общими сведениями преобразуются в обычные текстовые файлы со следующим форматом имени: `about_topic_name.help.txt`.
Содержимое Markdown должно соответствовать требованию схемы PlatyPS. `New-ExternalHelp` завершается с ошибками, если содержимое не соответствует схеме. Чтобы устранить нарушения схемы, необходимо изменить файлы.

> [!CAUTION]
> PlatyPS не очень хорошо преобразует файлы `about_*.md` в обычный текст. Чтобы получить приемлемые результаты, используйте очень простой Markdown. Файлы можно хранить в обычном текстовом формате `about_topic_name.help.txt`, чтобы PlatyPS не пришлось их преобразовывать.

После завершения этого шага вы увидите файлы `*-help.xml` и `about_*.help.txt` в целевой выходной папке.

Дополнительные сведения см. в разделе [New-ExternalHelp][].

### <a name="test-the-compiled-help-files"></a>Тестирование скомпилированных файлов справки

Вы можете проверить содержимое с помощью командлета [Get-HelpPreview][].

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

Командлет считывает скомпилированный файл MAML и выводит содержимое в том же формате, что и `Get-Help`. Это позволяет проверить результаты, чтобы убедиться, что файлы Markdown скомпилированы правильно и дают нужные результаты. Если обнаружена ошибка, снова измените файлы Markdown и перекомпилируйте MAML.

Теперь все готово для публикации файлов справки.

## <a name="publishing-your-help"></a>Публикация справки

Теперь, когда файлы Markdown скомпилированы в файлы справки PowerShell, вы можете представить их пользователям. Существует два варианта предоставления справки в консоли PowerShell.

- Упаковка файлов справки с помощью модуля.
- Создание обновляемого пакета справки, который пользователи устанавливают с помощью командлета `Update-Help`.

### <a name="packaging-help-with-the-module"></a>Упаковка справки по модулю

Файлы справки можно упаковать в собственный модуль. Дополнительные сведения о структуре папок см. в разделе [Написание справки для модулей][]. Необходимо включить список файлов справки в значение ключа **FileList** в манифесте модуля.

### <a name="creating-an-updateable-help-package"></a>Создание обновляемого пакета справки

В общих чертах, необходимо выполнить следующие действия по созданию обновляемой справки.

1. Поиск веб-сайта для размещения файлов справки.
1. Добавление ключа **HelpInfoURI** в манифест модуля.
1. Создание XML-файла HelpInfo.
1. Создание CAB-файлов.
1. Отправка файлов.

Дополнительные сведения см. в разделе [Поддержка обновляемой справки: пошаговые инструкции][step-by-step].

PlatyPS помогает выполнить некоторые из этих действий.

**HelpInfoURI** — это URL-адрес, указывающий на расположение, где файлы справки размещаются в Интернете. Это значение настраивается в манифесте модуля. `Update-Help` считывает манифест модуля для получения этого URL-адреса и загрузки обновляемого содержимого справки. Этот URL-адрес должен указывать только на расположение папки, а не на отдельные файлы. `Update-Help` создает имена файлов для загрузки на основе других сведений из манифеста модуля и XML-файла HelpInfo.

> [!IMPORTANT]
> **HelpInfoURI** должен заканчиваться символом прямой косой черты (`/`). Без этого символа `Update-Help` не сможет создать правильные пути к файлам для скачивания содержимого. Кроме того, большинство файловых служб на основе HTTP учитывают регистр. Метаданные модуля в XML-файле HelpInfo должны содержать правильный регистр букв.

Командлет `New-ExternalHelp` создает XML-файл HelpInfo в выходной папке. XML-файл HelpInfo строится с помощью метаданных YAML, содержащихся в файлах Markdown модуля (`ModuleName.md`).

Командлет `New-ExternalHelpCab` создает ZIP- и CAB-файлы, содержащие скомпилированные файлы MAML и `about_*.help.txt`. CAB-файлы совместимы со всеми версиями PowerShell.
В PowerShell 6 и более поздних версий можно использовать ZIP-файлы.

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

После создания ZIP- и CAB-файлов отправьте файлы ZIP, CAB и XML HelpInfo на файловый сервер HTTP. Разместите файлы в расположении, указанном **HelpInfoURI**.

Дополнительные сведения см. в разделе [New-ExternalHelpCab][].

### <a name="other-publishing-options"></a>Другие варианты публикации

Markdown — это универсальный формат, который легко преобразовать в другие форматы для публикации. С помощью такого средства, как [Pandoc][], можно преобразовать файлы справки Markdown в различные форматы документов, включая обычный текст, HTML, PDF и Office.

Кроме того, командлеты [ConvertFrom-Markdown][] и [Show-Markdown][] в PowerShell 6 и более поздних версий можно использовать для преобразования Markdown в HTML или создания цветового отображения в консоли PowerShell.

## <a name="known-issues"></a>Известные проблемы

Для PlatyPS очень важна [схема][] структуры создаваемых и компилируемых файлов Markdown. Допустимый Markdown вполне может нарушать эту схему. Дополнительные сведения см. в [руководстве по стилю PowerShell][] и разделе о [редактировании справочных статей][].

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Руководство по стилю для PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[Изменение справочных статей]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Написание справки для модулей]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
