---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 846aca6974190863a073773fe5148f0c57d77dc3
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388201"
---
# <span data-ttu-id="fd9db-103">Export-ODataEndpointProxy</span><span class="sxs-lookup"><span data-stu-id="fd9db-103">Export-ODataEndpointProxy</span></span>

## <span data-ttu-id="fd9db-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fd9db-104">SYNOPSIS</span></span>
<span data-ttu-id="fd9db-105">Создает модуль, содержащий командлеты для управления конечной точкой OData.</span><span class="sxs-lookup"><span data-stu-id="fd9db-105">Generates a module that contains cmdlets to manage an OData endpoint.</span></span>

## <span data-ttu-id="fd9db-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd9db-106">SYNTAX</span></span>

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd9db-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd9db-107">DESCRIPTION</span></span>

<span data-ttu-id="fd9db-108">`Export-ODataEndpointProxy`Командлет использует метаданные конечной точки OData для создания модуля, содержащего командлеты, которые можно использовать для управления этой конечной точкой OData.</span><span class="sxs-lookup"><span data-stu-id="fd9db-108">The `Export-ODataEndpointProxy` cmdlet uses the metadata of an OData endpoint to generate a module that contains cmdlets you can use to manage that OData endpoint.</span></span> <span data-ttu-id="fd9db-109">Модуль основан на CDXML.</span><span class="sxs-lookup"><span data-stu-id="fd9db-109">The module is based on CDXML.</span></span> <span data-ttu-id="fd9db-110">После того как этот командлет создаст модуль, он сохранит этот модуль в пути и имени файла, заданного параметром **аутпутмодуле** .</span><span class="sxs-lookup"><span data-stu-id="fd9db-110">After this cmdlet generates the module, it saves that module to the path and file name specified by the **OutputModule** parameter.</span></span>

<span data-ttu-id="fd9db-111">`Export-ODataEndpointProxy` создает командлеты для операций создания, чтения, обновления и удаления (CRUD), действий, не связанных с CRUD, и операций сопоставления.</span><span class="sxs-lookup"><span data-stu-id="fd9db-111">`Export-ODataEndpointProxy` generates cmdlets for create, read, update, and delete (CRUD) operations, non-CRUD actions, and association manipulation.</span></span>

<span data-ttu-id="fd9db-112">`Export-ODataEndpointProxy` создает один файл CDXML для каждого ресурса конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fd9db-112">`Export-ODataEndpointProxy` generates one CDXML file per endpoint resource.</span></span> <span data-ttu-id="fd9db-113">Эти файлы CDXML можно изменить после создания модуля.</span><span class="sxs-lookup"><span data-stu-id="fd9db-113">You can edit these CDXML files after the module is generated.</span></span> <span data-ttu-id="fd9db-114">Например, если необходимо изменить имена существительных или глаголов командлетов, чтобы они были согласованы с рекомендациями по именованию командлетов Windows PowerShell, можно изменить файл.</span><span class="sxs-lookup"><span data-stu-id="fd9db-114">For example, if you want to change the noun or verb names of the cmdlets to align with Windows PowerShell cmdlet naming guidelines, you can modify the file.</span></span>

<span data-ttu-id="fd9db-115">Каждый командлет в созданном модуле должен включать параметр **ConnectionURI** , чтобы подключиться к конечной точке, управляемой модулем.</span><span class="sxs-lookup"><span data-stu-id="fd9db-115">Every cmdlet in a generated module must include a **ConnectionURI** parameter in order to connect to the endpoint that the module manages.</span></span>

## <span data-ttu-id="fd9db-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="fd9db-116">EXAMPLES</span></span>

### <span data-ttu-id="fd9db-117">Пример 1. Создание модуля для управления конечной точкой веб-службы розничной торговли</span><span class="sxs-lookup"><span data-stu-id="fd9db-117">Example 1: Generate a module to manage a retail web service endpoint</span></span>

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

<span data-ttu-id="fd9db-118">Эта команда создает модуль для управления конечной точкой розничной службы.</span><span class="sxs-lookup"><span data-stu-id="fd9db-118">This command generates a module to manage a retail service endpoint.</span></span> <span data-ttu-id="fd9db-119">Команда задает универсальный код ресурса (URI) конечной точки и URI метаданных конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fd9db-119">The command specifies the URI of the endpoint and the URI of the endpoint metadata.</span></span> <span data-ttu-id="fd9db-120">Команда также предоставляет путь вывода и имя модуля скрипта в качестве значения параметра **аутпутмодуле** .</span><span class="sxs-lookup"><span data-stu-id="fd9db-120">The command also provides an output path and script module name as the value of the **OutputModule** parameter.</span></span> <span data-ttu-id="fd9db-121">Для значения параметра **ресаурценамемаппинг** команда предоставляет хэш-таблицу, которая сопоставляет имя коллекции ресурсов с нужным существительным для набора командлетов.</span><span class="sxs-lookup"><span data-stu-id="fd9db-121">For the value of the **ResourceNameMapping** parameter, the command provides a hashtable that maps the resource collection name to the desired noun for the cmdlet set.</span></span> <span data-ttu-id="fd9db-122">В этом примере Products — это имя коллекции ресурсов, **а «товары»** — это существительное.</span><span class="sxs-lookup"><span data-stu-id="fd9db-122">In this example, Products is the resource collection name and **Merchandise** is the noun.</span></span> <span data-ttu-id="fd9db-123">Чтобы разрешить подключения к узлам без SSL, HTTP, а не HTTPS, добавьте параметр **алловунсекуреконнектион** .</span><span class="sxs-lookup"><span data-stu-id="fd9db-123">To allow connections to non-SSL sites, HTTP, as opposed to HTTPS, add the **AllowUnsecureConnection** parameter.</span></span>

## <span data-ttu-id="fd9db-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd9db-124">PARAMETERS</span></span>

### <span data-ttu-id="fd9db-125">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="fd9db-125">-AllowClobber</span></span>

<span data-ttu-id="fd9db-126">Указывает, что этот командлет заменяет существующий модуль.</span><span class="sxs-lookup"><span data-stu-id="fd9db-126">Indicates that this cmdlet replaces an existing module.</span></span>

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

### <span data-ttu-id="fd9db-127">-Алловунсекуреконнектион</span><span class="sxs-lookup"><span data-stu-id="fd9db-127">-AllowUnsecureConnection</span></span>

<span data-ttu-id="fd9db-128">Указывает, что этот модуль может подключаться к URI, не защищенным с использованием SSL.</span><span class="sxs-lookup"><span data-stu-id="fd9db-128">Indicates that this module can connect to URIs that are not SSL-secured.</span></span> <span data-ttu-id="fd9db-129">Модуль может управлять сайтами HTTP в дополнение к сайтам HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd9db-129">The module can manage HTTP sites in addition to HTTPS sites.</span></span>

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

### <span data-ttu-id="fd9db-130">-Кмдлетадаптер</span><span class="sxs-lookup"><span data-stu-id="fd9db-130">-CmdletAdapter</span></span>

<span data-ttu-id="fd9db-131">Указывает адаптер командлета.</span><span class="sxs-lookup"><span data-stu-id="fd9db-131">Specifies the cmdlet adapter.</span></span> <span data-ttu-id="fd9db-132">Допустимые значения для этого параметра: Одатаадаптер и Нетворкконтроллерадаптер.</span><span class="sxs-lookup"><span data-stu-id="fd9db-132">The acceptable values for this parameter are: ODataAdapter and NetworkControllerAdapter.</span></span>

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

### <span data-ttu-id="fd9db-133">-Креатерекуестмесод</span><span class="sxs-lookup"><span data-stu-id="fd9db-133">-CreateRequestMethod</span></span>

<span data-ttu-id="fd9db-134">Указывает метод запроса.</span><span class="sxs-lookup"><span data-stu-id="fd9db-134">Specifies the request method.</span></span> <span data-ttu-id="fd9db-135">Допустимые значения для этого параметра: размещение, публикация и исправление.</span><span class="sxs-lookup"><span data-stu-id="fd9db-135">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

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

### <span data-ttu-id="fd9db-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="fd9db-136">-Credential</span></span>

<span data-ttu-id="fd9db-137">Указывает учетную запись пользователя, имеющую доступ к конечной точке OData.</span><span class="sxs-lookup"><span data-stu-id="fd9db-137">Specifies a user account that has access to the OData endpoint.</span></span> <span data-ttu-id="fd9db-138">Значение по умолчанию: текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="fd9db-138">The default value is the current user.</span></span> <span data-ttu-id="fd9db-139">Если удаленный компьютер работает под управлением Windows Vista или более поздней версии операционной системы Windows, командлет запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fd9db-139">If a remote computer runs Windows Vista or a later release of the Windows operating system, the cmdlet prompts you for credentials.</span></span>

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

### <span data-ttu-id="fd9db-140">-CustomData</span><span class="sxs-lookup"><span data-stu-id="fd9db-140">-CustomData</span></span>

<span data-ttu-id="fd9db-141">Указывает хэш-таблицу пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="fd9db-141">Specifies a hash table of custom data.</span></span>

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

### <span data-ttu-id="fd9db-142">-Force</span><span class="sxs-lookup"><span data-stu-id="fd9db-142">-Force</span></span>

<span data-ttu-id="fd9db-143">Указывает, что этот командлет перезаписывает существующий созданный модуль с тем же именем в существующей `Modules` папке.</span><span class="sxs-lookup"><span data-stu-id="fd9db-143">Indicates that this cmdlet overwrites an existing generated module of the same name in an existing `Modules` folder.</span></span>

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

### <span data-ttu-id="fd9db-144">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="fd9db-144">-Headers</span></span>

<span data-ttu-id="fd9db-145">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="fd9db-145">Specifies the headers of the web request.</span></span> <span data-ttu-id="fd9db-146">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="fd9db-146">Enter a hash table or dictionary.</span></span>

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

### <span data-ttu-id="fd9db-147">-Метадатаури</span><span class="sxs-lookup"><span data-stu-id="fd9db-147">-MetadataUri</span></span>

<span data-ttu-id="fd9db-148">Указывает универсальный код ресурса (URI) метаданных конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fd9db-148">Specifies the URI of the metadata of the endpoint.</span></span>

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

### <span data-ttu-id="fd9db-149">-Аутпутмодуле</span><span class="sxs-lookup"><span data-stu-id="fd9db-149">-OutputModule</span></span>

<span data-ttu-id="fd9db-150">Указывает путь и имя модуля, в который этот командлет сохраняет созданный модуль команд прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="fd9db-150">Specifies the path and module name to which this cmdlet saves the generated module of proxy commands.</span></span>

<span data-ttu-id="fd9db-151">Этот командлет копирует двоичный модуль, манифест модуля и файл форматирования, если применимо, в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="fd9db-151">This cmdlet copies a binary module, module manifest, and formatting file, if applicable, to the specified folder.</span></span> <span data-ttu-id="fd9db-152">Если указать только имя модуля, `Export-ODataEndpointProxy` то сохраняет модуль в `$home\Documents\WindowsPowerShell\Modules` папке.</span><span class="sxs-lookup"><span data-stu-id="fd9db-152">If you specify only the name of the module, `Export-ODataEndpointProxy` saves the module in the `$home\Documents\WindowsPowerShell\Modules` folder.</span></span> <span data-ttu-id="fd9db-153">Если указать путь, командлет создаст папку Module в этом пути.</span><span class="sxs-lookup"><span data-stu-id="fd9db-153">If you specify a path, the cmdlet creates the module folder in that path.</span></span>

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

### <span data-ttu-id="fd9db-154">-Ресаурценамемаппинг</span><span class="sxs-lookup"><span data-stu-id="fd9db-154">-ResourceNameMapping</span></span>

<span data-ttu-id="fd9db-155">Указывает хэш-таблицу, содержащую сопоставления, которые позволяют настроить созданные командлеты.</span><span class="sxs-lookup"><span data-stu-id="fd9db-155">Specifies a hashtable that contains mappings that let you customize the generated cmdlets.</span></span> <span data-ttu-id="fd9db-156">В этой таблице Hashtable имя коллекции ресурсов является ключом.</span><span class="sxs-lookup"><span data-stu-id="fd9db-156">In this hashtable, the resource collection name is the key.</span></span> <span data-ttu-id="fd9db-157">Требуемое существительное — это значение.</span><span class="sxs-lookup"><span data-stu-id="fd9db-157">The desired cmdlet noun is the value.</span></span>

<span data-ttu-id="fd9db-158">Например, в хэш-таблице `@{Products = 'Merchandise'}` **Products** — это имя коллекции ресурсов, которое служит ключом.</span><span class="sxs-lookup"><span data-stu-id="fd9db-158">For example, in the hash table `@{Products = 'Merchandise'}`, **Products** is the resource collection name that serves as the key.</span></span> <span data-ttu-id="fd9db-159">« **Товары** » — это результирующая существительное командлет.</span><span class="sxs-lookup"><span data-stu-id="fd9db-159">**Merchandise** is the resulting cmdlet noun.</span></span> <span data-ttu-id="fd9db-160">Имена созданных командлетов могут не совпадать с рекомендациями по именованию командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd9db-160">The generated cmdlet names might not align to Windows PowerShell cmdlet naming guidelines.</span></span> <span data-ttu-id="fd9db-161">Можно изменить файл CDXML ресурсов, чтобы изменить имена командлетов после того, как этот командлет создаст модуль.</span><span class="sxs-lookup"><span data-stu-id="fd9db-161">You can modify the resource CDXML file to change the cmdlet names after this cmdlet creates the module.</span></span> <span data-ttu-id="fd9db-162">Дополнительные сведения см. в разделе [рекомендации по разработке строго](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span><span class="sxs-lookup"><span data-stu-id="fd9db-162">For more information, see [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span></span>

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

### <span data-ttu-id="fd9db-163">-Упдатерекуестмесод</span><span class="sxs-lookup"><span data-stu-id="fd9db-163">-UpdateRequestMethod</span></span>

<span data-ttu-id="fd9db-164">Указывает метод запроса на обновление.</span><span class="sxs-lookup"><span data-stu-id="fd9db-164">Specifies the update request method.</span></span> <span data-ttu-id="fd9db-165">Допустимые значения для этого параметра: размещение, публикация и исправление.</span><span class="sxs-lookup"><span data-stu-id="fd9db-165">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

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

### <span data-ttu-id="fd9db-166">— URI</span><span class="sxs-lookup"><span data-stu-id="fd9db-166">-Uri</span></span>

<span data-ttu-id="fd9db-167">Указывает универсальный код ресурса (URI) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fd9db-167">Specifies the URI of the endpoint.</span></span>

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

### <span data-ttu-id="fd9db-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd9db-168">-Confirm</span></span>

<span data-ttu-id="fd9db-169">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="fd9db-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd9db-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd9db-170">-WhatIf</span></span>

<span data-ttu-id="fd9db-171">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="fd9db-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fd9db-172">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fd9db-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd9db-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fd9db-173">CommonParameters</span></span>

<span data-ttu-id="fd9db-174">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd9db-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd9db-175">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd9db-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd9db-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fd9db-176">INPUTS</span></span>

## <span data-ttu-id="fd9db-177">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fd9db-177">OUTPUTS</span></span>

## <span data-ttu-id="fd9db-178">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fd9db-178">NOTES</span></span>

## <span data-ttu-id="fd9db-179">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fd9db-179">RELATED LINKS</span></span>

<span data-ttu-id="fd9db-180">[Библиотека OData](/previous-versions/dotnet/wcf-data-services/hh525392(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="fd9db-180">[OData Library](/previous-versions/dotnet/wcf-data-services/hh525392(v=vs.103))</span></span>

[<span data-ttu-id="fd9db-181">Что такое протокол OData?</span><span class="sxs-lookup"><span data-stu-id="fd9db-181">What is the OData Protocol?</span></span>](https://www.odata.org/)

[<span data-ttu-id="fd9db-182">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="fd9db-182">Invoke-RestMethod</span></span>](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
