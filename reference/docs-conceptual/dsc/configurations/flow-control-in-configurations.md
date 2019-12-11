---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954081"
---
# <a name="conditional-statements-and-loops-in-configurations"></a>Условные операторы и циклы в конфигурациях

Вы можете сделать свои [конфигурации](configurations.md) более динамичными с помощью ключевых слов управления потоком PowerShell. В этой статье показано использование условных операторов и циклов для более динамичной конфигурации. Комбинирование условий и циклов с [параметрами](add-parameters-to-a-configuration.md) и [данными конфигурации](configData.md) обеспечивает большую гибкость и контроль при компиляции конфигураций.

Вы можете использовать любой язык PowerShell в конфигурации так же, как функцию или блок скриптов. Используемые вами операторы будут оцениваться только при вызове конфигурации для компиляции MOF-файла. В приведенных ниже примерах показаны простые сценарии для демонстрации концепций. Условия — это циклы, которые чаще всего используются с параметрами и данными конфигурации.

В этом простом примере блок ресурсов **Служба** извлекает текущее состояние службы во время компиляции, чтобы создать MOF-файл, который сохраняет свое текущее состояние.

> [!NOTE]
> Использование динамических блоков ресурсов снизит эффективность Intellisense. Анализатор PowerShell не может определить, являются ли указанные значения приемлемыми, пока конфигурация не будет скомпилирована.

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

Вы также можете создавать конфигурации только для тех компьютеров, которые подключены к сети, используя простую инструкцию `if`.

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
> Блоки динамических ресурсов в приведенных выше примерах ссылаются на текущий компьютер. В этом случае это будет компьютер, на котором вы создаете конфигурацию, а не целевой узел.

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>Сводка

Таким образом в конфигурации можно использовать любой язык PowerShell.

Это включает в себя следующие вещи:

- пользовательские объекты;
- хэш-таблицы;
- управление строками;
- Удаленное взаимодействие
- инструментарий WMI и CIM;
- объекты ActiveDirectory;
- и другое…

Любой код PowerShell, определенный в конфигурации, будет оцениваться во время компиляции, но вы также можете поместить код в сценарий, содержащий вашу конфигурацию. Любой код за пределами блока конфигурации будет выполняться при импорте вашей конфигурации.

## <a name="see-also"></a>См. также:

- [Добавление параметров в конфигурацию](add-parameters-to-a-configuration.md)
- [Разделение данных конфигурации из конфигураций](configData.md)
