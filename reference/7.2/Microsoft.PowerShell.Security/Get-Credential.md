---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 5630c4d09a2806eb117d005466d4925c1740d3a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604558"
---
# Get-Credential

## Краткий обзор
Возвращает объект учетных данных на основе имени пользователя и пароля.

## SYNTAX

### CredentialSet (по умолчанию)

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### MessageSet

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Credential`Командлет создает объект учетных данных для указанного имени пользователя и пароля. Объект учетных данных можно использовать в операциях безопасности.

`Get-Credential`Командлет запрашивает у пользователя пароль или имя пользователя и пароль. С помощью параметра **Message** можно указать настраиваемое сообщение в командной строке командной строки.

## Примеры

### Пример 1

```powershell
$c = Get-Credential
```

Эта команда возвращает объект учетных данных и сохраняет его в `$c` переменной.

При вводе команды вам будет предложено ввести имя пользователя и пароль. При вводе запрошенной информации командлет создает объект **PSCredential** , представляющий учетные данные пользователя, и сохраняет его в `$c` переменной.

Вы можете использовать этот объект в качестве входных данных в командлетах, запрашивающих проверку подлинности пользователя, например командлеты с параметром **Credential**. Однако некоторые поставщики, установленные с помощью PowerShell, не поддерживают параметр **Credential** .

### Пример 2

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

Эти команды используют объект учетных данных, `Get-Credential` возвращаемый командлетом для проверки подлинности пользователя на удаленном компьютере, чтобы он мог использовать инструментарий управления Windows (WMI) (WMI) для управления компьютером.

Первая команда получает объект учетных данных и сохраняет его в `$c` переменной. Вторая команда использует объект Credential в `Get-CimInstance` команде. Эта команда получает сведения о дисках на компьютере Server01.

### Пример 3

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

Эта команда показывает, как включить `Get-Credential` команду в  `Get-CimInstance` команду.

Эта команда использует `Get-CimInstance` командлет для получения сведений о BIOS на компьютере Server01. Он использует параметр **Credential** для проверки подлинности пользователя, Domain01\User01 и `Get-Credential` команды в качестве значения параметра **Credential** .

### Пример 4

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

В этом примере создаются учетные данные, в которые входит имя пользователя без доменного имени.

Первая команда получает учетные данные с именем пользователя USER01 и сохраняет их в `$c` переменной.
Вторая команда отображает значение свойства **Username** полученного объекта учетных данных.

### Пример 5

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

Эта команда использует метод **PromptForCredential**, чтобы запросить у пользователя его имя пользователя и пароль. Команда сохраняет итоговые учетные данные в `$Credential` переменной.

Метод **PromptForCredential** является альтернативой использованию `Get-Credential` командлета. При использовании **PromptForCredential** можно указать заголовок, сообщения и имя пользователя, которые отображаются в командной строке.

Дополнительные сведения см. в документации по [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) в пакете SDK.

### Пример 6

В этом примере показано, как создать объект учетных данных, идентичный объекту, который `Get-Credential` возвращает данные без запроса пользователя. Для этого метода требуется незашифрованный пароль, который может нарушать стандарты безопасности в некоторых организациях.

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

Первая команда сохраняет имя учетной записи пользователя в `$User` параметре. Значение должно иметь формат "домен\пользователь" или "имя компьютера\пользователь".

Вторая команда использует `ConvertTo-SecureString` командлет для создания защищенной строки из текстового пароля. Параметр **AsPlainText** команды указывает, что строка является обычным текстом, а параметр **Force** подтверждает, что вы понимаете риски использования обычного текста.

Третья команда использует `New-Object` командлет для создания объекта **PSCredential** на основе значений в `$User` `$PWord` переменных и.

### Пример 7

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

Эта команда использует параметры **Message** и **username** `Get-Credential` командлета. Этот формат команды предназначен для общих скриптов и функций. В этом случае в сообщении пользователю указывается причина необходимости учетных данных и подтверждается санкционированность запроса.

### Пример 8

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

Эта команда получает учетные данные с удаленного компьютера Server01. Команда использует `Invoke-Command` командлет для выполнения `Get-Credential` команды на удаленном компьютере. В выходных данных отображается удаленное сообщение безопасности, которое `Get-Credential` включается в запрос проверки подлинности.

## PARAMETERS

### -Credential

Указывает имя пользователя для учетных данных, например **User01** или **Domain01\User01**. Имя параметра `-Credential` является необязательным.

Когда вы отправляете команду и указываете имя пользователя, вам будет предложено ввести пароль. Если опустить этот параметр, будет предложено ввести имя пользователя и пароль.

Начиная с PowerShell 3,0, если ввести имя пользователя без домена, `Get-Credential` перед именем не будет вставляться обратная косая черта.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Message

Указывает сообщение, которое отображается в запросе проверки подлинности. Этот параметр предназначен для использования в функции или скрипте. В сообщении можно объяснить пользователю причину запроса учетных данных и способ их использования.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Задает текст строки заголовка для запроса проверки подлинности в консоли.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Указывает имя пользователя. В запросе проверки подлинности необходимо указать пароль для имени пользователя. По умолчанию имя пользователя является пустым, а в запросе проверки подлинности требуется указать как имя пользователя, так и пароль.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

В этот командлет нельзя передать входные данные.

## Выходные данные

### System.Management.Automation.PSCredential

`Get-Credential` Возвращает объект учетных данных.

## ПРИМЕЧАНИЯ

Можно использовать объект **PSCredential** , который `Get-Credential` создает в командлетах, запрашивающих проверку подлинности пользователя, например, с помощью параметра **Credential** .

Параметр **Credential** не поддерживается всеми поставщиками, установленными с помощью PowerShell.
Начиная с PowerShell 3,0, он поддерживается для командлетов SELECT, таких как `Get-Content` `New-PSDrive` командлеты и.

## Связанные ссылки

[PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
