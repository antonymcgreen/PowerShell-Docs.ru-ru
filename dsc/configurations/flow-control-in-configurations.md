---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402315"
---
# <a name="conditional-statements-and-loops-in-configurations"></a>Условные операторы и циклы в конфигурациях

Можно сделать ваши [конфигураций](configurations.md) более динамичными, с помощью ключевых слов PowerShell управления потоком. В этой статье мы покажем, как можно использовать условные операторы и циклы выполняются ваши настройки более динамичной. Условное объединение и циклы с [параметры](add-parameters-to-a-configuration.md) и [данные конфигурации](configData.md) обеспечивает дополнительную гибкость и контроль при компиляции конфигурации.

Так же, как функции или блок скрипта можно использовать любой язык PowerShell, в конфигурации. Инструкции, которые используются вычисляется только в том случае, при вызове конфигурации для компиляции MOF «-» файла. В приведенных ниже примерах показано простых сценариев для демонстрации концепций. Условные выражения — это циклы чаще всего используются с параметрами и данные конфигурации.

В этом простом примере **службы** блоке ресурсов возвращает текущее состояние службы во время компиляции для создания файла «.mof», его текущее состояние.

> [!NOTE]
> С помощью динамические блоки ресурсов сосредоточенной эффективность Intellisense. Средство синтаксического анализа PowerShell не может определить, если значения, указанные являются допустимыми, пока не компиляции конфигурации.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

Кроме того, можно создать **службы** блокировка ресурсов для каждой службы на текущем компьютере, с помощью `foreach` цикла.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

Также только для создания конфигурации для компьютеров, которые находятся в сети, с помощью простого `if` инструкции.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    Foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> Динамический ресурс блоков в приведенной выше схеме примеры текущего компьютера. В этом экземпляре, который может быть компьютер, вы создаете конфигурации, не конечный узел.

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>Сводка

Таким образом можно использовать любой язык PowerShell, в конфигурации.

Сюда входят, например:

- Пользовательские объекты
- Хэш-таблицы
- Управление строками
- Удаленное взаимодействие
- WMI и CIM
- ActiveDirectory объектов
- и другое…

Любой код PowerShell, определенный в конфигурации будет вычисляться как время компиляции, но можно также поместить код в скрипт, содержащий конфигурацию. Никакого кода за пределами блока конфигурации будет выполняться при импорте конфигурации.

## <a name="see-also"></a>См. также:

- [Добавление параметров в конфигурацию](add-parameters-to-a-configuration.md)
- [Разделение данных конфигурации из конфигураций](configData.md)
