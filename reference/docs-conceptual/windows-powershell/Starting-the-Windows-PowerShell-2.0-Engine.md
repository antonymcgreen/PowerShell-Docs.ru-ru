---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Использование подсистемы Windows PowerShell 2.0
ms.openlocfilehash: c5ac92159d63e5669643908016186ed32dfb46db
ms.sourcegitcommit: 3e343f005fe76960c998ef1869a1a093d37ef349
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85216028"
---
# <a name="using-the-windows-powershell-20-engine"></a>Использование подсистемы Windows PowerShell 2.0

Windows PowerShell предназначена для обратной совместимости с предыдущими версиями оболочки. Командлеты, поставщики, оснастки, модули и сценарии, написанные для Windows PowerShell 2.0, выполняются в более новых версиях Windows PowerShell без изменений. Однако в Microsoft .NET Framework 4 изменена политика активации среды выполнения.
Основные программы Windows PowerShell, написанные для Windows PowerShell 2.0 и скомпилированные с помощью CLR 2.0, не могут выполняться без изменения в новых версиях Windows PowerShell, скомпилированных с помощью CLR 4.0 (или более поздних версий).

Подсистема Windows PowerShell 2.0 предназначена для использования только в том случае, если выполнение существующего сценария или существующей основной программы невозможно из-за несовместимости с Windows PowerShell 5.1. Примерами являются более старые версии модулей Exchange или SQL Server. Такие ситуации довольно редки.

Многие программы, требующие использования подсистемы Windows PowerShell 2.0, запускают ее автоматически. Эти инструкции предназначены для редких случаев, когда подсистему необходимо запустить вручную.

## <a name="deprecation-and-security-concerns"></a>Прекращение поддержки и соображения безопасности

Поддержка Windows PowerShell 2.0 была прекращена в августе 2017 г. Дополнительные сведения см. в [объявлении][] в блоге, посвященном PowerShell.

В Windows PowerShell 2.0 отсутствует целый ряд функций усиления защиты и обеспечения безопасности, добавленных в версии 3, 4 и 5. Настоятельно рекомендуется не использовать эту версию продукта. Дополнительные сведения см. [A Comparison of Shell and Scripting Language Security][] и в [этой записи блога][blueteam].

## <a name="installing-and-enabling-required-programs"></a>Установка и включение требуемых программ

Перед запуском подсистемы Windows PowerShell 2.0 включите подсистему Windows PowerShell 2.0 и Microsoft .NET Framework 3.5 с пакетом обновления 1. Инструкции см. в статье [Установка Windows PowerShell][].

Системы, где установлена Windows Management Framework 3.0 или более поздние версии, имеют все необходимые компоненты. Никакая дополнительная настройка не требуется. Дополнительные сведения об установке Windows Management Framework см. в статье [Установка и настройка WMF][].

## <a name="how-to-start-the-windows-powershell-20-engine"></a>Запуск подсистемы Windows PowerShell 2.0

При запуске Windows PowerShell по умолчанию открывается самая новая версия. Для запуска Windows PowerShell с подсистемой Windows PowerShell 2.0 используйте параметр Version в `PowerShell.exe`. Команду можно выполнить в любой командной строке, включая Windows PowerShell и Cmd.exe.

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a>Запуск удаленного сеанса с помощью подсистемы Windows PowerShell 2.0

Чтобы запустить подсистему Windows PowerShell 2.0 в удаленном сеансе, создайте конфигурацию сеанса (которая также называется _конечной точкой_) на удаленном компьютере, которая загружает подсистему Windows PowerShell 2.0. Конфигурация сеанса сохраняется на удаленном компьютере; любой авторизованный пользователь может использовать ее для создания сеансов на основе Windows PowerShell 2.0.

Это сложная задача, которая обычно выполняется системным администратором.

Следующая процедура использует параметр **PSVersion** командлета [Register-PSSessionConfiguration][] для создания конфигурации сеанса с подсистемой Windows PowerShell 2.0. Можно также использовать параметр **PowerShellVersion** командлета [New-PSSessionConfigurationFile][], чтобы создать файл конфигурации для сеанса, который загружает подсистему Windows PowerShell 2.0, и параметр **PSVersion** командлета [Set-PSSessionConfiguration][], чтобы изменить конфигурацию сеанса для использования подсистемы Windows PowerShell 2.0.

Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files][].
Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations][].

### <a name="to-start-a-remote-windows-powershell-20-session"></a>Запуск удаленного сеанса Windows PowerShell 2.0

1. Для создания конфигурации сеанса, требующей подсистемы Windows PowerShell 2.0, используйте параметр **PSVersion** командлета `Register-PSSessionConfiguration` со значением `2.0`.
   Выполните команду на компьютере на "стороне сервера" или на принимающей стороне подключения.

   Следующий пример команды создает конфигурацию сеанса PS2 на компьютере Server01. Чтобы выполнить эту команду, запустите Windows PowerShell с параметром **Запуск от имени администратора**.

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. Чтобы создать на компьютере Server01 сеанс, использующий конфигурацию сеанса PS2, примените параметр **ConfigurationName** для командлетов, создающих удаленный сеанс, таких как New-PSSession.

   При запуске сеанса, использующего конфигурацию, подсистема Windows PowerShell 2.0 автоматически загружается в него.

   Следующая команда запускает сеанс на компьютере Server01, который использует конфигурацию PS2. Сеанс сохраняется в переменную `$s`.

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a>Запуск фонового задания с помощью подсистемы Windows PowerShell 2.0

Чтобы запустить фоновое задание с помощью подсистемы Windows PowerShell 2.0, используйте параметр **PSVersion** командлета [Start-Job][].

Следующая команда запускает фоновое задание с помощью подсистемы Windows PowerShell 2.0:

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs][].

<!-- link references -->
[объявлении]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/ (Сравнение безопасности оболочки и языка сценариев)
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Установка Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Установка и настройка WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
