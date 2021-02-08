---
title: Новые возможности PowerShell 7.1
description: Новые возможности и изменения в PowerShell 7.1
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577213"
---
# <a name="whats-new-in-powershell-71"></a>Новые возможности PowerShell 7.1

11 ноября 2020 г. мы [объявили](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) о выпуске общедоступной версии PowerShell 7.1. Основываясь на фундаменте, заложенном в PowerShell 7.0, мы уделили больше внимания проблемам сообщества и реализовали ряд усовершенствований и исправлений. Мы стремимся поддерживать высокую стабильность и производительность платформы PowerShell.

Ниже перечислены новые функции, обновления и критические изменения в PowerShell 7.1.

- PSReadLine 2.1.0 с прогнозной технологией IntelliSense
- Версия PowerShell 7.1 опубликована в Microsoft Store.
- Пакеты установщика обновлены для новых версий ОС с поддержкой ARM64.
- 4 новые экспериментальные функции; 2 экспериментальные функции стали основными.
- Несколько критических изменений для повышения удобства использования

Полный список изменений доступен в [журнале изменений](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) в репозитории GitHub.

## <a name="psreadline-210"></a>PSReadLine 2.1.0

Кроме того, PowerShell 7.1 включает версию PSReadLine 2.1.0. В ней реализована прогнозная технология IntelliSense. Дополнительные сведения о прогнозной технологии IntelliSense см. в [объявлении](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/), опубликованном в блоге PowerShell.

## <a name="microsoft-store-installer-package"></a>Пакет установщика в Microsoft Store

Версия PowerShell 7.1 опубликована в Microsoft Store. Этот выпуск PowerShell можно найти на веб-сайте [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) или в приложении Store в ОС Windows.

Пакет Microsoft Store обеспечивает следующие преимущества:

- автоматические обновления, встроенные в основной механизм Windows 10;
- интеграция с другими механизмами распространения программного обеспечения, такими как Intune и SCCM.

> [!NOTE]
> Параметры конфигурации системного уровня, хранящиеся в `$PSHOME`, нельзя изменить. Это относится и к конфигурации WSMAN. Это означает, что вы не сможете подключать удаленные сеансы к установкам PowerShell на основе хранилища. Поддерживаются конфигурации уровня пользователя и удаленное взаимодействие по SSH.

## <a name="other-installers"></a>Другие установщики

Более актуальные сведения о поддерживаемых операционных системах и жизненном цикле поддержки см. в статье [Жизненный цикл поддержки PowerShell](/powershell/scripting/powershell-support-lifecycle).

Обратитесь к инструкциям по установке для своей операционной системы:

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

Кроме того, PowerShell 7.1 поддерживает выпуски Debian и Ubuntu для ARM32 и ARM64, а также Alpine Linux для ARM64.

Сообщество также предоставило пакеты для [Arch](https://aur.archlinux.org/packages/powershell/) и Kali Linux, хотя они не поддерживаются официально.

> [!NOTE]
> Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine и ARM сейчас не поддерживают удаленное взаимодействие WinRM. Подробные сведения о настройке удаленного взаимодействия на основе SSH см. в статье [Удаленное взаимодействие с PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="experimental-features"></a>Экспериментальные возможности

Дополнительные сведения см. в статье об [использовании экспериментальных функций](../learn/experimental-features.md).

В этом выпуске следующие экспериментальные функции стали основными:

- [PSNullConditionalOperators](../learn/experimental-features.md#psnullconditionaloperators)
- [PSUnixFileStat](../learn/experimental-features.md#psunixfilestat)

В этом выпуске были добавлены следующие экспериментальные функции:

- [Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - В PowerShell 7.1 эта экспериментальная функция расширена: ко всем командлетам `*-PSBreakpoint` добавлен параметр **Runspace**. Параметр **Runspace** указывает объекту **Runspace** взаимодействовать с точками останова в указанном пространстве выполнения.

- [PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) — эта функция позволяет передавать пути к поставщикам PowerShell в собственные команды, которые не поддерживают синтаксис путей PowerShell.

- [PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) — когда левый операнд в инструкции оператора `-replace` не является строкой, он преобразуется в строку. Когда эта функция включена, при преобразовании строк не используются настройки языка и региональных параметров.

- [PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) — основа для поддержки будущих подключаемых модулей с прогнозной технологией IntelliSense.

## <a name="breaking-changes-and-improvements"></a>Критические изменения и улучшения

- Исправлено ошибочное значение `$false` для `$?` при записи собственной команды в `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395)).

  Обычно, когда собственные команды выполняют запись в `stderr`, им не нужно сообщать об ошибке.
  В результате этого изменения `$?` задается равным `$false` только в том случае, если собственная команда имеет ненулевой код выхода. Это изменение не связано с экспериментальной функцией `PSNotApplyErrorActionToStderr`.

- Теперь `$ErrorActionPreference` не влияет на выходные данные `stderr` собственных команд ([#13361](https://github.com/PowerShell/PowerShell/pull/13361)).

  Обычно, когда собственные команды выполняют запись в `stderr`, им не нужно сообщать об ошибке.
  В результате этого изменения выходные данные `stderr` по-прежнему фиксируются в объектах **ErrorRecord**, но среда выполнения больше не применяет `$ErrorActionPreference`, если **ErrorRecord** поступает от собственной команды.

- Параметр `-FromUnixTime` переименован в `-UnixTimeSeconds` в `Get-Date`, чтобы разрешить ввод времени в формате Unix ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (отдельная благодарность @aetos382!).

  Параметр `-FromUnixTime` был добавлен в версии 7.1-preview.2. Он был переименован, чтобы лучше соответствовать типу данных. Этот параметр принимает целочисленное значение, которое представляет время в секундах с 0:00:00 1 января 1970 г.

  В этом примере время в формате Unix (представленное количеством секунд с 0:00:00 01.01.1970) преобразуется в тип DateTime.

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- Разрешено переопределять явно заданным именованным параметром аналогичный параметр из сплаттинга хэш-таблицы (#13162)

  В результате этого изменения именованные параметры, передаваемые через сплаттинг, перемещаются в конец списка параметров, так что они привязываются после привязки всех явно указанных именованных параметров. При привязке параметров в простых функциях не возникает ошибка, если не удается найти указанный именованный параметр. Неизвестные именованные параметры привязываются к параметру `$args` простой функции. Перемещение сплаттинга в конец списка аргументов приводит к изменению порядка, в котором параметры следуют в `$args`.

  Пример:

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  В предыдущем случае аргумент **MyPath** не привязан к `-Path`, так как он является третьим в списке аргументов. ## В результате он помещается в '$args' вместе с `Blah = "World"`

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  В результате этого изменения аргументы из `@hash` перемещаются в конец списка аргументов. **MyPath** становится первым аргументом в списке, поэтому он привязывается к `-Path`.

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- Параметр переключателя `-Qualifier` теперь не зависит от позиции в `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (отдельная благодарность @yecril71pl!).

- Рабочий каталог разрешается для `Start-Process` как литеральный путь, если он не указан ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (отдельная благодарность @NoMoreFood!).

- Параметр `-OutFile` теперь ведет себя в веб-командлетах как `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (отдельная благодарность @iSazonov!).

- Исправлена привязка параметра строки для числовых литералов `BigInteger` ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (отдельная благодарность @vexx32!).

- В Windows `Start-Process` позволяет создать среду процесса со всеми переменными среды из текущего сеанса, а при использовании `-UseNewEnvironment` создается новая среда процесса по умолчанию ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (отдельная благодарность @iSazonov!).

- Устранен перенос возвращаемого результата в `PSObject` при преобразовании `ScriptBlock` в делегат ([#10619](https://github.com/PowerShell/PowerShell/pull/10619)).

  Когда `ScriptBlock` преобразуется в тип делегата для использования в контексте C#, перенос результата в `PSObject` приводит к ненужным проблемам.

  - Когда значение преобразуется в возвращаемый тип-делегат, `PSObject` по сути разворачивается. Поэтому `PSObject` не требуется.
  - Если возвращаемый тип-делегат — `object`, он переносится в `PSObject`, что затрудняет работу с ним в коде C#.

  В результате этого изменения возвращается базовый объект.
