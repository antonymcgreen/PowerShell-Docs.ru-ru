---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227810"
---
# Export-ODataEndpointProxy

## Краткий обзор
Создает модуль, содержащий командлеты для управления конечной точкой OData.

## SYNTAX

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-ODataEndpointProxy`Командлет использует метаданные конечной точки OData для создания модуля, содержащего командлеты, которые можно использовать для управления этой конечной точкой OData. Модуль основан на CDXML. После того как этот командлет создаст модуль, он сохранит этот модуль в пути и имени файла, заданного параметром **аутпутмодуле** .

`Export-ODataEndpointProxy` создает командлеты для операций создания, чтения, обновления и удаления (CRUD), действий, не связанных с CRUD, и операций сопоставления.

`Export-ODataEndpointProxy` создает один файл CDXML для каждого ресурса конечной точки. Эти файлы CDXML можно изменить после создания модуля. Например, если необходимо изменить имена существительных или глаголов командлетов, чтобы они были согласованы с рекомендациями по именованию командлетов Windows PowerShell, можно изменить файл.

Каждый командлет в созданном модуле должен включать параметр **ConnectionURI** , чтобы подключиться к конечной точке, управляемой модулем.

## Примеры

### Пример 1. Создание модуля для управления конечной точкой веб-службы розничной торговли

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

Эта команда создает модуль для управления конечной точкой розничной службы. Команда задает универсальный код ресурса (URI) конечной точки и URI метаданных конечной точки. Команда также предоставляет путь вывода и имя модуля скрипта в качестве значения параметра **аутпутмодуле** . Для значения параметра **ресаурценамемаппинг** команда предоставляет хэш-таблицу, которая сопоставляет имя коллекции ресурсов с нужным существительным для набора командлетов. В этом примере Products — это имя коллекции ресурсов, **а «товары»** — это существительное. Чтобы разрешить подключения к узлам без SSL, HTTP, а не HTTPS, добавьте параметр **алловунсекуреконнектион** .

## PARAMETERS

### -AllowClobber

Указывает, что этот командлет заменяет существующий модуль.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Алловунсекуреконнектион

Указывает, что этот модуль может подключаться к URI, не защищенным с использованием SSL. Модуль может управлять сайтами HTTP в дополнение к сайтам HTTPS.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Кмдлетадаптер

Указывает адаптер командлета. Допустимые значения для этого параметра: Одатаадаптер и Нетворкконтроллерадаптер.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Креатерекуестмесод

Указывает метод запроса. Допустимые значения для этого параметра: размещение, публикация и исправление.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую доступ к конечной точке OData. Значение по умолчанию: текущий пользователь. Если удаленный компьютер работает под управлением Windows Vista или более поздней версии операционной системы Windows, командлет запрашивает учетные данные.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomData

Указывает хэш-таблицу пользовательских данных.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет перезаписывает существующий созданный модуль с тем же именем в существующей `Modules` папке.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Заголовки

Задает заголовки веб-запроса. Введите словарь или хэш-таблицу.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Метадатаури

Указывает универсальный код ресурса (URI) метаданных конечной точки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Аутпутмодуле

Указывает путь и имя модуля, в который этот командлет сохраняет созданный модуль команд прокси-сервера.

Этот командлет копирует двоичный модуль, манифест модуля и файл форматирования, если применимо, в указанную папку. Если указать только имя модуля, `Export-ODataEndpointProxy` то сохраняет модуль в `$home\Documents\WindowsPowerShell\Modules` папке. Если указать путь, командлет создаст папку Module в этом пути.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ресаурценамемаппинг

Указывает хэш-таблицу, содержащую сопоставления, которые позволяют настроить созданные командлеты. В этой таблице Hashtable имя коллекции ресурсов является ключом. Требуемое существительное — это значение.

Например, в хэш-таблице `@{Products = 'Merchandise'}` **Products** — это имя коллекции ресурсов, которое служит ключом. « **Товары** » — это результирующая существительное командлет. Имена созданных командлетов могут не совпадать с рекомендациями по именованию командлетов Windows PowerShell. Можно изменить файл CDXML ресурсов, чтобы изменить имена командлетов после того, как этот командлет создаст модуль. Дополнительные сведения см. в разделе [рекомендации по разработке строго](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Упдатерекуестмесод

Указывает метод запроса на обновление. Допустимые значения для этого параметра: размещение, публикация и исправление.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — URI

Указывает универсальный код ресурса (URI) конечной точки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Библиотека OData](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)

[Что такое протокол OData?](https://www.odata.org/)

[Invoke-RestMethod](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
