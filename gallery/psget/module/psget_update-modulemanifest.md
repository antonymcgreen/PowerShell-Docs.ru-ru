# Update-ModuleManifest
Обновляет файл манифеста модуля.

## Описание

Командлет Update-ModuleManifest обновляет файл манифеста модуля (PSD1).

### Заметки
    - DscResourcesToExport is only supported on the latest PowerShell version 5.0. We won’t be able to update the field if you are running on lower versions of PowerShell.

## Синтаксис командлета
```powershell
Get-Command -Name Update-ModuleManifest -Module PowerShellGet -Syntax
```

## Ссылка на раздел справки по командлету в Интернете

[Update-ModuleManifest](http://go.microsoft.com/fwlink/?LinkId=619311)

## Примеры команд

Этот новый командлет используется для обновления файла манифеста с помощью входных значений свойств. Он принимает все те же параметры, что и New-ModuleManifest.

Нам известно, что многие создатели модулей стремятся указать "\*" в экспортированных значениях, таких как FunctionsToExport, CmdletsToExport и т. д. Во время публикации модуля в коллекции PowerShell неуказанные функции и команды будут занесены неправильно. Поэтому мы рекомендуем авторам модулей обновить манифесты с использованием соответствующих значений.

При наличии модулей, имеющих экспортированные свойства, Update-ModuleManifest заполнит указанный файл манифеста данными из экспортированных функций, командлетов, переменных и т. п:
```powershell
Get-Content -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
@{
# Script module or binary module file associated with this manifest.
# RootModule = ''
# Version number of this module.
ModuleVersion = '2.5'
# ID used to uniquely identify this module
GUID = '610e5c5b-dc42-4eaa-8511-ebfb44066d5e'

#(Other properties removed here for Simplicity…)

# Functions to export from this module
FunctionsToExport = '*'
# Cmdlets to export from this module
CmdletsToExport = '*'
# Variables to export from this module
VariablesToExport = '*'
# Aliases to export from this module
AliasesToExport = '*'
}
```

После Update-ModuleManifest:
```powershell
Update-ModuleManifest -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
Get-Content -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
#
# Module manifest for module 'NewManifest'
#
# Generated by: author name
#
# Generated on: 11/13/2015
#
@{
# Script module or binary module file associated with this manifest.
# RootModule = ''
# Version number of this module.
ModuleVersion = '2.5'
# ID used to uniquely identify this module
GUID = '610e5c5b-dc42-4eaa-8511-ebfb44066d5e'
# Functions to export from this module
FunctionsToExport = 'Get-FooFn Get-FooWF'
# Cmdlets to export from this module
CmdletsToExport = 'Test-PSGetTestCmdlet'
}
```

Для каждого модуля имеются сопоставленные с ним поля метаданных. Для правильного отображения метаданных в коллекции PowrShell можно воспользоваться Update-ModuleManifest, чтобы заполнить эти поля в PrivateData.

```powershell
Update-ModuleManifest -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1" -Tags "Tag1" -LicenseUri "http://license.com" -ProjectUri "http://project.com" -IconUri "http://icon.com" -ReleaseNotes "Test module"
```

Хэш-таблица PrivateData из шаблона файла манифеста имеет следующие свойства.

```powershell
# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{
    PSData = @{
        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''
    
        # A URL to the main website for this project.
        # ProjectUri = ''
        
        # A URL to an icon representing this module.
        # IconUri = ''
        
        # ReleaseNotes of this module
        # ReleaseNotes = ''
        
        # External dependent modules of this module
        # ExternalModuleDependencies = ''
    } # End of PSData hashtable
} # End of PrivateData hashtable
```



<!--HONumber=Aug16_HO3-->

