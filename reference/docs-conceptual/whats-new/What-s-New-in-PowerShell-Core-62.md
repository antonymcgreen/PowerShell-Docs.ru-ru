---
title: Новые возможности в PowerShell Core 6.2
description: Новые возможности и изменения в PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 2224d23a244175059a705c07001e8ad8d6ab3aa0
ms.sourcegitcommit: 8dd4394cf867005a8b9ef0bb74b744c964fbc332
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "58750059"
---
# <a name="whats-new-in-powershell-core-62"></a>Новые возможности в PowerShell Core 6.2

Ниже указаны некоторые основные новые функции и изменения, которые были внесены в PowerShell Core 6.2.

Кроме того, доступно **множество** добавлений, позволяющих повысить быстродействие и стабильность PowerShell (а также целый ряд исправлений ошибок).
Полный список изменений см. в нашем [журнале изменений на сайте GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).

Несмотря на то что далее мы называем лишь часть имен, мы выражаем благодарность [всем участникам сообщества](https://github.com/PowerShell/PowerShell/graphs/contributors), которые внесли свой вклад в этот выпуск.

## <a name="engine-updates-and-fixes"></a>Обновления и исправления модулей

- Добавлен командлет удаленного включения или отключения предупреждающих сообщений PowerShell ([#9203][]).
- Исправлена ошибка с регрессией удаленной десериализации `FormatTable` ([#9116][]).
- Обновлены API `async` на основе задач, добавленные в PowerShell для получения объекта задачи напрямую ([#9079][]).
- Добавлено 5 перегрузок `InvokeAsync` и `StopAsync` для типа `PowerShell` ([#8056][]) (спасибо @KirkMunro!).

## <a name="general-cmdlet-updates-and-fixes"></a>Общие обновления и исправления командлетов

- Включены командлеты `SecureString` для отличающихся от Windows продуктов с сохранением обычного текста ([#9199][]).
- Добавлено устаревшее сообщения для `Send-MailMessage` ([#9178][]).
- Исправлена ошибка с `Restart-Computer` при работе с `localhost` и отсутствием WinRM ([#9160][]).
- В `Start-Job` включено получение неустранимой ошибки при размещении PowerShell ([#9128][]).
- Обновлена версия для `PowerShell.Native` для размещения тестов ([#8983][]).

## <a name="breaking-changes"></a>Критические изменения

Исправлено поведение NoEnumerate в сценариях Write-Output для согласования с Windows PowerShell ([#9069][]) (спасибо @vexx32!).

<!-- Link references -->
[#8056]: https://github.com/PowerShell/PowerShell/pull/8056
[#8983]: https://github.com/PowerShell/PowerShell/pull/8983
[#9069]: https://github.com/PowerShell/PowerShell/pull/9069
[#9079]: https://github.com/PowerShell/PowerShell/pull/9079
[#9116]: https://github.com/PowerShell/PowerShell/pull/9116
[#9128]: https://github.com/PowerShell/PowerShell/pull/9128
[#9160]: https://github.com/PowerShell/PowerShell/pull/9160
[#9178]: https://github.com/PowerShell/PowerShell/pull/9178
[#9199]: https://github.com/PowerShell/PowerShell/pull/9199
[#9203]: https://github.com/PowerShell/PowerShell/pull/9203
