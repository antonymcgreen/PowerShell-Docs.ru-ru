---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс Script в DSC
description: Ресурс Script в DSC
ms.openlocfilehash: f404bf3137caa9f57ad56034895cb15c8944ec07
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142979"
---
# <a name="dsc-script-resource"></a>Ресурс Script в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс `Script` в DSC Windows PowerShell предоставляет механизм запуска блоков сценариев на целевых узлах. Ресурс `Script` использует свойства `GetScript`
`SetScript` и `TestScript`, которые содержат блоки скрипта, определяемые вами для выполнения соответствующих операций DSC.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Синтаксис

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> Блоки `GetScript`, `TestScript` и `SetScript` хранятся в виде строк.

## <a name="properties"></a>Свойства

|  Свойство  |                                          Описание                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| GetScript  | Блок скрипта, который возвращает текущее состояние узла.                                    |
| SetScript  | Блок скрипта, который DSC использует для обеспечения совместимости, если узел не находится в нужном состоянии. |
| TestScript | Блок скрипта, который определяет, находится ли узел в нужном состоянии.                           |
| Учетные данные | Указывает учетные данные, используемые для запуска этого сценария, если они необходимы.        |

## <a name="common-properties"></a>Общие свойства

|       Свойство       |                                            Описание                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| DependsOn            | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. |
| PsDscRunAsCredential | Задает учетные данные для выполнения всего ресурса от другого имени.                                           |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

### <a name="additional-information"></a>Дополнительные сведения

#### <a name="getscript"></a>GetScript

DSC не использует выходные данные из `GetScript`. Командлет [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) выполняет `GetScript`, чтобы получить сведения о текущем состоянии узла. Не требуется возвращаемое значение из `GetScript`. Если вы указываете возвращаемое значение, используйте хэш-таблицу с ключом **Result** со строковым значением.

#### <a name="testscript"></a>TestScript

DSC выполняет `TestScript`, чтобы определить, необходим ли запуск `SetScript`. Если `TestScript` возвращает `$false`, DSC выполняет `SetScript`, чтобы вернуть узел в нужное состояние. Этот блок скрипта должен возвращать логическое значение. Значение `$true` указывает, что узел совместим и `SetScript` запускать не нужно.

Командлет [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) выполняет `TestScript`, чтобы получить сведения о совместимости узлов с ресурсами `Script`. Но в этом случае `SetScript` не будет запущен независимо от того, какое значение возвращает блок `TestScript`.

> [!NOTE]
> Все выходные данные `TestScript` являются частью его возвращаемого значения. PowerShell интерпретирует нескрытые выходные данные как ненулевое значение, поэтому `TestScript` вернет `$true` независимо от состояния узла. Это приводит к непредсказуемым результатам, ложноположительным значениям и сложностям при устранении неполадок.

#### <a name="setscript"></a>SetScript

`SetScript` изменяет узел, задавая ему требуемое состояние. Он вызывается DSC, если блок `TestScript` возвращает значение `$false`. `SetScript` не имеет возвращаемого значения.

## <a name="examples"></a>Примеры

### <a name="example-1-write-sample-text-using-a-script-resource"></a>Пример 1: написание примера текста с помощью ресурса Script

Этот пример проверяет наличие `C:\TempFolder\TestFile.txt` на каждом узле. Если такой файл не существует, он создается с помощью `SetScript`. `GetScript` возвращает содержимое файла, а его возвращаемое значение не используется.

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a>Пример 2. Сравнение сведений о версии с помощью ресурса Script

В этом примере из текстового файла на исходном компьютере извлекаются сведения о _соответствующей_ версии, которые сохраняются в переменной `$version`. При создании MOF-файла узла DSC заменяет переменные `$using:version` в каждом блоке сценария значением переменной `$version`.
Во время выполнения сведения о _соответствующей_ версии сохраняются в текстовом файле на каждом узле. При последующих выполнениях эти сведения сравниваются и обновляются.

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a>Пример 3. Использование параметров в ресурсе Script

В этом примере осуществляется доступ к параметрам из ресурса Script с использованием области `using`.
Обратите внимание, что аналогичным образом можно получить доступ к **ConfigurationData** . Как и в примере 2, ожидается сохраненная версия в локальном файле на целевом узле. Можно настроить как локальный путь к файлу, так и версию, что позволяет отделить код от данных конфигурации.

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

Полученный MOF-файл включает переменные и их значения, доступ к которым осуществляется через область `using`.
Они вставляются в каждый блок scriptblock, использующий переменные. Сценарии Test и Set были удалены для краткости:

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a>Известные ограничения

- Учетные данные, передаваемые в рамках ресурса скрипта, не всегда являются надежными при использовании серверной модели извлечения или принудительной отправки. В этом случае рекомендуется использовать полный ресурс, а не ресурс скрипта.
