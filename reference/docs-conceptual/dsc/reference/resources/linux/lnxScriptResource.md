---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxScript в DSC для Linux
ms.openlocfilehash: e39808e110d5ee4bf9d0ccd418ca3b15ac9fe420
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463658"
---
# <a name="dsc-for-linux-nxscript-resource"></a>Ресурс nxScript в DSC для Linux

Ресурс **nxScript** в DSC PowerShell предоставляет механизм управления сценариями Linux на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|GetScript |Предоставляет скрипт для возврата сведений о текущем состоянии компьютера. Этот скрипт выполняется при вызове скрипта [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer). Сценарий должен начинаться со знака решетки, например `#!/bin/bash`. |
|SetScript |Предоставляет скрипт, с помощью которого компьютер переходит в надлежащее состояние. При вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) в первую очередь выполняется команда **TestScript**. Если блок **TestScript** возвращает код выхода, отличный от 0, запускается блок **SetScript**. Если блок **TestScript** возвращает код выхода 0, **SetScript** не выполняется. Сценарий должен начинаться со знака решетки, например `#!/bin/bash`. |
|TestScript |Предоставляет скрипт для оценки состояния узла. Этот скрипт выполняется при вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer). Если он возвращает код выхода, отличный от 0, выполняется команда **SetScript**. Если он возвращает код выхода 0, команда **SetScript** не выполняется. Кроме того, **TestScript** выполняется при вызове скрипта [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer). Однако в этом случае **SetScript** не будет запущен, какое бы значение ни вернул блок **TestScript**. Блок **TestScript** должен содержать контент и возвращать код выхода 0, если фактическая конфигурация соответствует текущей настройке требуемого состояния, и другой код выхода, если они не совпадают. Текущей конфигурацией требуемого состояния является последняя конфигурация, активированная на узле, который использует DSC. Сценарий должен начинаться со знака решетки, например `#!/bin/bash`. |
|Пользователь |Указывает, от имени какого пользователя выполняется сценарий. |
|Группа |Указывает, от имени какой группы выполняется сценарий. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |

## <a name="example"></a>Пример

В следующем примере показано применение ресурса **nxScript** для дополнительного управления конфигурацией.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
