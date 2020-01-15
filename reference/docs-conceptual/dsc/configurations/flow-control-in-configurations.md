---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 86f75be4a3d1c1760dd6269335431e8ab9fd8d09
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736902"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a>Условные операторы и циклы в конфигурации

Вы можете сделать свою [конфигурацию](configurations.md) более динамичной с помощью ключевых слов управления потоком PowerShell. В этой статье показано использование условных операторов и циклов для более динамичной `Configuration`. Комбинирование условных операторов и циклов с [параметрами](add-parameters-to-a-configuration.md) и [данными конфигурации](configData.md) обеспечивает большую гибкость и контроль при компиляции `Configuration`.

Вы можете использовать любую возможность языка PowerShell в `Configuration` так же, как функцию или блок скриптов.
Используемые вами операторы будут оцениваться только при вызове `Configuration` для компиляции файла `.mof`. В приведенных ниже примерах показаны сценарии для демонстрации концепций. Условные операторы и циклы чаще всего используются с параметрами и данными конфигурации.

В этом примере блок ресурсов **Служба** извлекает текущее состояние службы во время компиляции, чтобы создать файл `.mof`, который сохраняет свое текущее состояние.

> [!NOTE]
> Использование динамических блоков ресурсов снизит эффективность Intellisense. Анализатор PowerShell не может определить, являются ли указанные значения приемлемыми, пока `Configuration` не будет скомпилирована.

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

Кроме того, вы можете создать блок ресурса **Служба** для каждой службы на текущем компьютере, используя цикл `foreach`.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        foreach ($service in $(Get-Service))
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

Вы также можете создавать `Configuration` только для тех компьютеров, которые подключены к сети, используя оператор `if`.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
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
> Блоки динамических ресурсов в приведенных выше примерах ссылаются на текущий компьютер. В этом случае это будет компьютер, на котором вы создаете `Configuration`, а не целевой узел.

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>Сводка

Таким образом в `Configuration` можно использовать любую возможность языка PowerShell.

Это включает в себя следующие вещи:

- пользовательские объекты;
- хэш-таблицы;
- управление строками;
- Удаленное взаимодействие
- инструментарий WMI и CIM;
- объекты ActiveDirectory;
- и другое…

Любой код PowerShell, определенный в `Configuration`, оценивается во время компиляции, но вы также можете поместить код в скрипт, содержащий вашу `Configuration`. Любой код за пределами блока `Configuration` выполняется при импорте вашей `Configuration`.

## <a name="see-also"></a>См. также раздел

- [Добавление параметров в конфигурацию](add-parameters-to-a-configuration.md)
- [Разделение данных конфигурации из конфигураций](configData.md)
