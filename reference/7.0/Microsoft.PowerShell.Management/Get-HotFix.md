---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 355257d0e403143d6983886de592d491241c6253
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226902"
---
# Get-HotFix

## Краткий обзор
Возвращает исправления, установленные на локальных или удаленных компьютерах.

## SYNTAX

### Default (по умолчанию)

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### Описание

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## DESCRIPTION

`Get-Hotfix`Командлет получает исправления или обновления, установленные на локальном компьютере или на указанных удаленных компьютерах. Обновления могут устанавливаться Центр обновления Windows, Центр обновления Майкрософт, Windows Server Update Services или вручную.

## Примеры

### Пример 1. получение всех исправлений на локальном компьютере

`Get-Hotfix`Командлет возвращает все исправления, установленные на локальном компьютере.

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### Пример 2. получение исправлений с нескольких компьютеров, отфильтрованных по строке

`Get-Hotfix`Команда использует параметры для получения исправлений, установленных на удаленных компьютерах. Результаты фильтруются по указанной строке описания.

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

`Get-Hotfix` фильтрует выходные данные с помощью параметра **Description** и строки **безопасности** , включающей `*` подстановочный знак звездочки (). Параметр **ComputerName** включает строку имен удаленных компьютеров с разделителями-запятыми. Параметр **Credential** указывает учетную запись пользователя, имеющую разрешение на доступ к удаленным компьютерам и командам выполнения.

### Пример 3. Проверка установки обновления и запись имен компьютеров в файл

Команды в этом примере проверяют, установлено ли конкретное обновление. Если обновление не установлено, имя компьютера записывается в текстовый файл.

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

`$A`Переменная содержит имена компьютеров, полученные `Get-Content` из текстового файла. Объекты в `$A` отправляются по конвейеру в `ForEach-Object` . `if`Оператор использует `Get-Hotfix` командлет с параметром **ID** и конкретным идентификатором для каждого имени компьютера. Если на компьютере не установлен указанный идентификатор исправления, `Add-Content` командлет записывает имя компьютера в файл.

### Пример 4. Получение последнего исправления на локальном компьютере

В этом примере возвращается последнее исправление, установленное на компьютере.

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

`Get-Hotfix` отправляет объекты по конвейеру в `Sort-Object` командлет. `Sort-Object` Сортирует объекты по возрастанию и использует параметр **Property** для вычисления каждой **установить** даты. В нотации массива `[-1]` выбирается последнее установленное исправление.

## PARAMETERS

### -ComputerName

Указывает удаленный компьютер. Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.

Если параметр **ComputerName** не указан, `Get-Hotfix` выполняется на локальном компьютере.

Параметр **ComputerName** не зависит от удаленного взаимодействия Windows PowerShell. Если компьютер не настроен для выполнения удаленных команд, используйте параметр **ComputerName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд. Значение по умолчанию — текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

`Get-HotFix` использует параметр **Description** для указания типов исправлений. Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id

Фильтрует `Get-HotFix` результаты для конкретных идентификаторов исправлений. Подстановочные знаки не принимаются.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Строка

Одно или несколько имен компьютеров можно передать в командлет Get-HotFix по конвейеру.

## Выходные данные

### System. Management. ManagementObject # root\CIMV2\ Win32_QuickFixEngineering

`Get-HotFix` Возвращает объекты, представляющие исправления на компьютере.

## ПРИМЕЧАНИЯ

[Класс WMI](/windows/desktop/WmiSdk/retrieving-a-class) **Win32_QuickFixEngineering** представляет небольшое обновление на уровне системы, которое обычно называется обновлением QFE, которое применяется к текущей операционной системе. Этот класс возвращает только обновления, предоставляемые компонентом обслуживания на основе компонентов (CBS). Эти обновления не перечислены в реестре. Обновления, предоставляемые Microsoft установщик Windows (MSI) или [Центр обновления Windows](https://update.microsoft.com) сайте, не возвращаются **Win32_QuickFixEngineering**. Дополнительные сведения см. в разделе [класс Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).

`Get-HotFix`Выходные данные могут отличаться в разных операционных системах.

## Связанные ссылки

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Add-Content](Add-Content.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Класс Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
