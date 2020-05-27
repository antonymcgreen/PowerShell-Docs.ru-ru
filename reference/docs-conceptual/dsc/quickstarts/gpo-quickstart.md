---
ms.date: 07/09/2019
keywords: DSC,объект групповой политики,powershell,настройка,установка
title: Краткое руководство. Преобразование групповой политики в DSC
ms.openlocfilehash: a9ce9cecd71fe00d2908024a3ee474ec836af3ba
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808254"
---
# <a name="quickstart-convert-group-policy-into-dsc"></a>Краткое руководство. Преобразование групповой политики в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Конфигурацию DSC можно создать из групповой политики или базовых показателей Центра безопасности Azure. Модуль [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) содержит следующие команды для выполнения этих задач.

- `ConvertFrom-GPO` — преобразование групповых политик, которые хранятся в виде файлов. Можно также указать каталог, содержащий несколько политик, которые будут объединены в одну конфигурацию.
  - Чтобы экспортировать групповые политики в вашей среде, используйте командлет [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) или следуйте инструкциям в статье [Экспорт объекта групповой политики в файл](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).
- `ConvertFrom-SCM` — преобразование базовых показателей Security Compliance Manager, которые хранятся в виде `.xml`-файлов.
- `ConvertFrom-ASC` — преобразование базовых показателей Центра безопасности Azure, которые хранятся в виде `.json`-файлов.
- `Merge-GPOs` — преобразование групповой политики, которая применена на конечном компьютере.

Командлеты, перечисленные выше, преобразуют базовые показатели в `.mof`-файл DSC. Вы также можете создать сценарий конфигурации (`.ps1`), который можно изменять и перекомпилировать. Командлеты способны обнаружить ошибки компиляции при наличии отсутствующих ресурсов или повторяющихся блоков. Блоки ресурсов, способные привести к ошибкам компиляции, будут закомментированы.

В следующем примере выполняется преобразование [Microsoft Security Baseline](https://www.microsoft.com/en-us/download/details.aspx?id=55319) в сценарий конфигурации DSC (`.ps1`) и `.mof`-файл.

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

После выполнения команд, вы увидите два файла в каталоге вывода по умолчанию, созданные по текущему пути.

```powershell
Get-ChildItem -Path .\Output
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----         7/9/2019   9:35 AM   227.37KB DSCFromGPO.ps1
-a----         7/9/2019   9:35 AM   410.03KB localhost.mof
```

Каждый управляемый узел также потребует следующие два модуля.

- [SecurityPolicyDSC](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [AuditPolicyDSC](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> **BaselineManagement** — это решение, разработанное сообществом, чтобы сделать поддержку DSC более доступной. Решения сообщества поставляются разработчиками проекта, а не корпорацией Майкрософт. Вы можете открыть новую проблему по **BaselineManagement** на [GitHub](https://github.com/microsoft/BaselineManagement).

## <a name="next-steps"></a>Дальнейшие действия

- Чтобы отправить скрипт конфигурации в конфигурацию состояния службы автоматизации Azure, см. раздел [Приступая к работе](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).
- Добавьте модули **SecurityPolicyDSC** и **AuditPolicyDSC** в свою [учетную запись службы автоматизации](/azure/automation/shared-resources/modules).
- Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).
