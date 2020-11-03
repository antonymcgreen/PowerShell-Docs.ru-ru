---
description: Описывает файлы конфигурации сеанса, которые используются в конфигурации сеанса (также называемой конечной точкой) для определения среды сеансов, использующих конфигурацию сеанса.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 198a0aeb667c3c947bc7e202bc3c0d9832195b91
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231929"
---
# <a name="about-session-configuration-files"></a>Сведения о файлах конфигурации сеанса

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описывает файлы конфигурации сеанса, которые используются в конфигурации сеанса (также называемой конечной точкой) для определения среды сеансов, использующих конфигурацию сеанса.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

"Файл конфигурации сеанса" — это текстовый файл с расширением pssc, который содержит хэш-таблицу свойств и значений конфигурации сеанса. Для задания свойств конфигурации сеанса можно использовать файл конфигурации сеанса. Это определяет среду всех сеансов Windows PowerShell, использующих эту конфигурацию сеанса.

Файлы конфигурации сеанса упрощают создание пользовательских конфигураций сеансов без использования сложных сборок или скриптов C#.

"Конфигурация сеанса" или "конечная точка" — это коллекция параметров локального компьютера, определяющая, как пользователи могут создавать сеансы на компьютере. команды, которые пользователи могут выполнять в этих сеансах; и должен ли сеанс запускаться как привилегированная виртуальная учетная запись. Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).

Конфигурации сеансов появились в Windows PowerShell 2,0, а файлы конфигурации сеанса появились в Windows PowerShell 3,0. Для включения файла конфигурации сеанса в конфигурацию сеанса необходимо использовать Windows PowerShell 3,0. Тем не менее пользователи Windows PowerShell 2,0 (и более поздние версии) зависят от параметров в конфигурации сеанса.

## <a name="creating-custom-sessions"></a>Создание пользовательских сеансов

Вы можете настроить множество функций сеанса Windows PowerShell, указав свойства сеанса в конфигурации сеанса. Вы можете настроить сеанс, написав программу на C#, которая определяет пользовательское пространство выполнения, или можно использовать файл конфигурации сеанса для определения свойств сеансов, созданных с помощью конфигурации сеанса. В качестве общего правила проще использовать файл конфигурации сеанса, чем написание программы на C#.

Файл конфигурации сеанса можно использовать для создания таких элементов, как полнофункциональные сеансы для пользователей с высоким уровнем доверия. Заблокированные сеансы, которые обеспечивают минимальный доступ; сеансы, предназначенные для конкретных и содержащие только модули, необходимые для этих задач; и сеансы, в которых непривилегированные пользователи могут выполнять только определенные команды в качестве привилегированной учетной записи.

Помимо этого, можно управлять тем, могут ли пользователи сеанса использовать элементы языка Windows PowerShell, такие как блоки сценариев, или же они могут выполнять только команды. Можно управлять версией пользователей Windows PowerShell, которые могут выполняться в сеансе. Управление тем, какие модули импортируются в сеанс; и управлять тем, какие командлеты, функции и псевдонимы могут выполнять пользователи сеанса. При использовании поля RoleDefinitions можно предоставить пользователям различные возможности в сеансе на основе членства в группе.

Дополнительные сведения о RoleDefinitions и определении этого значения см. в разделе справки по командлету New-PSRoleCapabilityFile.

## <a name="creating-a-session-configuration-file"></a>Создание файла конфигурации сеанса

Самый простой способ создать файл конфигурации сеанса — с помощью командлета New-PSSessionConfigurationFile. Этот командлет создает файл, использующий правильный синтаксис и формат, который автоматически проверяет многие значения свойств файла конфигурации.

Подробное описание свойств, которые можно задать в файле конфигурации сеанса, см. в разделе справки по командлету New-PSSessionConfigurationFile.

Следующая команда создает файл конфигурации сеанса, в котором используются значения по умолчанию. В результирующем файле конфигурации используются только значения по умолчанию, так как в них включены параметры, отличные от параметра Path (который указывает путь к файлу).

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

Чтобы просмотреть новый файл конфигурации в текстовом редакторе по умолчанию, используйте следующую команду:

```powershell
Invoke-Item -Path .\Defaults.pssc
```

Чтобы создать конфигурацию сеанса для сеансов, в которых пользователь может выполнять команды, но не использовать другие элементы языка Windows PowerShell, введите:

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

В предыдущей команде Присвоение параметру Лангуажемоде значения "не язык" запрещает пользователям выполнять такие действия, как написание или выполнение скриптов, а также использование переменных.

Чтобы создать конфигурацию сеанса для сеансов, в которых пользователи могут использовать только командлеты Get, введите:

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

В предыдущем примере при присвоении параметру VisibleCmdlets значения GET-* ограничивается число пользователей командлетами, имена которых начинаются со строки со строковым значением Get-.

Чтобы создать конфигурацию сеанса для сеансов, работающих под привилегированной виртуальной учетной записью, а не учетных данных пользователя, введите:

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

Чтобы создать конфигурацию сеанса для сеансов, в которых команды, видимые пользователю, указаны в файле возможностей роли, введите:

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a>Использование файла конфигурации сеанса

Файл конфигурации сеанса можно включить во время создания конфигурации сеанса или добавить файл в конфигурацию сеанса позднее.

Чтобы включить файл конфигурации сеанса при создании конфигурации сеанса, используйте параметр Path командлета Register-PSSessionConfiguration.

Например, следующая команда использует файл языка pssc при создании конфигурации сеанса на основе языка.

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

Когда запускается новый сеанс на языке, пользователи получают доступ только к командам Windows PowerShell.

Чтобы добавить файл конфигурации сеанса в существующую конфигурацию сеанса, используйте командлет Set-PSSessionConfiguration и параметр path. Это влияет на все новые сеансы, созданные с помощью указанной конфигурации сеанса. Обратите внимание, что командлет Set-PSSessionConfiguration изменяет сам сеанс и не изменяет файл конфигурации сеанса.

Например, следующая команда добавляет файл. pssc в конфигурацию сеанса Локкеддовн.

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

Когда пользователи используют конфигурацию сеанса Локкеддовн для создания сеанса, они смогут выполнять командлеты, но они не смогут создавать или использовать переменные, назначать значения или использовать другие языковые элементы Windows PowerShell.

Следующая команда использует командлет New-PSSession для создания сеанса на компьютере SRV01, который использует конфигурацию сеанса Локкеддовн, сохраняя ссылку на объект в сеансе в переменной $s. Список управления доступом (ACL) конфигурации сеанса определяет, кто может использовать его для создания сеанса.

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

Так как ограничения языка не были добавлены в конфигурацию сеанса Локкеддовн, пользователи в сеансах Локкеддовн смогут выполнять только команды и командлеты Windows PowerShell. Например, следующие две команды используют командлет Invoke-Command для выполнения команд в сеансе, на который ссылается переменная $s. Первая команда, которая запускает командлет Get-UICulture и не использует переменные, выполняется с ошибкой. Вторая команда, которая получает значение переменной $PSUICulture, завершается ошибкой.

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a>Изменение файла конфигурации сеанса

Все параметры в конфигурации сеанса, за исключением RunAsVirtualAccount и Рунасвиртуалаккаунтграупс, могут быть изменены путем изменения файла конфигурации сеанса, используемого конфигурацией сеанса. Для этого сначала найдите активную копию файла конфигурации сеанса.

При использовании файла конфигурации сеанса в конфигурации сеанса Windows PowerShell создает активную копию файла конфигурации сеанса и сохраняет ее в \$ \\ каталоге pshome сессионконфиг на локальном компьютере.

Расположение активной копии файла конфигурации сеанса хранится в свойстве Конфигфилепас объекта конфигурации сеанса.

Следующая команда возвращает расположение файла конфигурации сеанса для конфигурации сеанса на языке.

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

Эта команда возвращает путь к файлу, аналогичный следующему:

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Файл. pssc можно изменить в любом текстовом редакторе. После сохранения файла он будет использоваться всеми новыми сеансами, которые используют конфигурацию сеанса.

Если необходимо изменить параметры RunAsVirtualAccount или Рунасвиртуалаккаунтграупс, необходимо отменить регистрацию конфигурации сеанса и повторно зарегистрировать файл конфигурации сеанса, содержащий измененные значения.

## <a name="testing-a-session-configuration-file"></a>Тестирование файла конфигурации сеанса

Используйте командлет Test-PSSessionConfigurationFile для тестирования файлов конфигурации сеанса, измененных вручную. Это важно. Если синтаксис и значения файла не являются допустимыми, пользователи не смогут использовать конфигурацию сеанса для создания сеанса.

Например, следующая команда проверяет файл конфигурации активного сеанса в конфигурации сеанса на языке.

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Если синтаксис и значения в файле конфигурации являются допустимыми Test-PSSessionConfigurationFile возвращает значение true. Если синтаксис и значения не являются допустимыми, командлет возвращает значение false.

Test-PSSessionConfigurationFile можно использовать для тестирования любого файла конфигурации сеанса, включая файлы, создаваемые командлетом New-PSSessionConfiguration. Дополнительные сведения см. в разделе справки по командлету Test-PSSessionConfigurationFile.

## <a name="removing-a-session-configuration-file"></a>Удаление файла конфигурации сеанса

Невозможно удалить файл конфигурации сеанса из конфигурации сеанса.
Однако можно заменить файл новым файлом, использующим параметры по умолчанию. Это фактически отменяет параметры, используемые исходным файлом конфигурации.

Чтобы заменить файл конфигурации сеанса, создайте новый файл конфигурации сеанса, который использует параметры по умолчанию, а затем используйте командлет Set-PSSessionConfiguration, чтобы заменить файл конфигурации пользовательского сеанса новым файлом.

Например, следующие команды создают файл конфигурации сеанса по умолчанию, а затем заменяют файл конфигурации активного сеанса в конфигурации сеанса на языке.

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

Когда эти команды будут завершены, конфигурация сеанса неязыкового интерфейса будет обеспечивать полную языковую поддержку (параметр по умолчанию) для всех сеансов, созданных с помощью этой конфигурации сеанса.

Просмотр свойств конфигурации сеанса. объекты конфигурации сеанса, представляющие конфигурации сеансов с помощью файлов конфигурации сеанса, имеют дополнительные свойства, которые упрощают обнаружение и анализ конфигурации сеанса. (Обратите внимание, что имя типа, приведенное ниже, включает в себя форматированное определение представления.) Свойства можно просмотреть, выполнив командлет Get-PSSessionConfiguration и передав возвращенные данные в командлет Get-Member:

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

Эти свойства упрощают поиск конкретных конфигураций сеансов.
Например, свойство ExecutionPolicy можно использовать для поиска конфигурации сеанса, которая поддерживает сеансы с политикой выполнения RemoteSigned.
Обратите внимание, что, поскольку свойство ExecutionPolicy существует только в сеансах, использующих файлы конфигурации сеанса, команда может не возвращать все конфигурации соответствующих сеансов.

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

Следующая команда получает конфигурации сеанса, в которых выполняющий является администратор Exchange.

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

Чтобы просмотреть сведения об определениях ролей, связанных с конфигурацией, используйте командлет Get-PSSessionCapability. Этот командлет позволяет определить команды и среду, доступные конкретным пользователям в конкретных конечных точках.

## <a name="notes"></a>ПРИМЕЧАНИЯ

Конфигурации сеансов также поддерживают тип сеанса, называемый пустым сеансом. Пустой тип сеанса позволяет создавать пользовательские сеансы с выбранными командами. Если не добавить модули, функции или скрипты в пустой сеанс, сеанс будет ограничен выражениями и может не быть ни в каких практических случаях использовать. Свойство SessionType указывает, работаете ли вы с пустым сеансом.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Session_Configurations](about_Session_Configurations.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Enable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[Get-PSSessionCapability](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[New-PSRoleCapabilityFile](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
