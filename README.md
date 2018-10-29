# <a name="microsoft-open-source-code-of-conduct"></a>Правила поведения: использование открытого исходного кода Майкрософт

Этот проект основывается на [правилах использования открытого исходного кода Майкрософт](https://opensource.microsoft.com/codeofconduct/).
Дополнительные сведения см. в [вопросах и ответах о правилах поведения](https://opensource.microsoft.com/codeofconduct/faq/) или обратитесь по адресу [opencode@microsoft.com](mailto:opencode@microsoft.com) с любыми дополнительными вопросами или комментариями.

[![Состояние сборки](https://ci.appveyor.com/api/projects/status/onshefxnc4g4pv87/branch/staging?svg=true)](https://ci.appveyor.com/project/PowerShell/powershell-docs/branch/staging)

## <a name="powershell-documentation"></a>Документация по PowerShell

Добро пожаловать в репозиторий PowerShell-Docs, в котором находится официальная документация по PowerShell.

## <a name="repository-structure"></a>Структура репозитория

Каждая из перечисленных ниже папок верхнего уровня содержит набор документации, которая опубликована на сайте [документации Майкрософт](https://docs.microsoft.com/powershell).

- [/developer/](https://docs.microsoft.com/powershell/developer/) — папка для будущей документации по пакету SDK PowerShell.
  - Сейчас мы переносим это содержимое с сайта MSDN.
- [/dsc/](https://docs.microsoft.com/powershell/dsc/) — для функции настройки требуемого состояния.
- [/gallery/](https://docs.microsoft.com/powershell/gallery) — для [коллекции PowerShell](https://www.powershellgallery.com/);
- [/jea/](https://docs.microsoft.com/powershell/jea/) — для функции Just Enough Administration (JEA);
- [/reference/](https://docs.microsoft.com/powershell/scripting/) — для концептуальных статей по PowerShell и справочной документации по модулям для версий 3.0, 4.0, 5.0, 5.1 и 6.0.
  - Это содержимое также служит источником справочных сведений, выводимых с помощью командлета `Get-Help`.
- [/wmf](https://docs.microsoft.com/powershell/wmf/readme) — содержит заметки о платформе Windows Management Framework (пакет, используемый для распространения новых версий PowerShell в предыдущих версиях Windows).

## <a name="contributing"></a>Публикация

Мы активно объединяем публикации в этом репозитории с помощью [запроса на включение внесенных изменений](https://help.github.com/articles/using-pull-requests/) в *промежуточной* ветви.
Примечание. Для того, чтобы сообщество свободно использовало ваши публикации, перед отправкой запроса на включение внесенных изменений необходимо [подписать соглашение Contribution License Agreement](https://cla.microsoft.com/).

Дополнительные сведения о публикации можно прочесть в [руководстве по публикациям](CONTRIBUTING.md).
Руководство по публикациям содержит подробные сведения об участии в составлении документации и рекомендуемых инструментах, а также требования к стилю и форматированию.
Используйте шаблоны "Проблема" и "Запрос на включение внесенных изменений", чтобы обеспечить согласованность документации по разным версиям.

## <a name="licenses"></a>Лицензии

Существует два файла лицензии для этого проекта.
Лицензия MIT применяется к коду, содержащемуся в этом репозитории.
Лицензия Creative Commons применяется к документации.