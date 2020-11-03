---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227453"
---
# <span data-ttu-id="bcc34-103">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bcc34-103">Test-DscConfiguration</span></span>

## <span data-ttu-id="bcc34-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bcc34-104">SYNOPSIS</span></span>
<span data-ttu-id="bcc34-105">Проверяет, соответствует ли фактическая конфигурация на узлах требуемой.</span><span class="sxs-lookup"><span data-stu-id="bcc34-105">Tests whether the actual configuration on the nodes matches the desired configuration.</span></span>

## <span data-ttu-id="bcc34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bcc34-106">SYNTAX</span></span>

### <span data-ttu-id="bcc34-107">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bcc34-107">ComputerNameSet (Default)</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### <span data-ttu-id="bcc34-108">компутернамеандпассет</span><span class="sxs-lookup"><span data-stu-id="bcc34-108">ComputerNameAndPathSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="bcc34-109">компутернамеандреференцеконфигуратионсет</span><span class="sxs-lookup"><span data-stu-id="bcc34-109">ComputerNameAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="bcc34-110">Цимсессионандпассет</span><span class="sxs-lookup"><span data-stu-id="bcc34-110">CimSessionAndPathSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="bcc34-111">Цимсессионандреференцеконфигуратионсет</span><span class="sxs-lookup"><span data-stu-id="bcc34-111">CimSessionAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="bcc34-112">Цимсессионсет</span><span class="sxs-lookup"><span data-stu-id="bcc34-112">CimSessionSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## <span data-ttu-id="bcc34-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bcc34-113">DESCRIPTION</span></span>
<span data-ttu-id="bcc34-114">Командлет **Test-DscConfiguration** проверяет, соответствует ли фактическая конфигурация на узлах требуемой.</span><span class="sxs-lookup"><span data-stu-id="bcc34-114">The **Test-DscConfiguration** cmdlet tests whether the actual configuration on the nodes matches the desired configuration.</span></span>
<span data-ttu-id="bcc34-115">Укажите компьютеры, для которых требуется проверить конфигурации, используя имена компьютеров или сеансы модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="bcc34-115">Specify which computers for which you want to test configurations by using computer names or Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="bcc34-116">Если целевой компьютер не указан, командлет проверяет конфигурацию локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bcc34-116">If you do not specify a target computer, the cmdlet tests configuration of the local computer.</span></span>

<span data-ttu-id="bcc34-117">Если требуемые и фактические конфигурации совпадают, командлет возвращает строковое значение "true".</span><span class="sxs-lookup"><span data-stu-id="bcc34-117">If the desired and actual configurations match, the cmdlet returns a string value of 'True'.</span></span>
<span data-ttu-id="bcc34-118">В противном случае возвращается строковое значение "false".</span><span class="sxs-lookup"><span data-stu-id="bcc34-118">Otherwise, it returns a string value of 'False'.</span></span>

## <span data-ttu-id="bcc34-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="bcc34-119">EXAMPLES</span></span>

### <span data-ttu-id="bcc34-120">Пример 1. Конфигурация теста для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="bcc34-120">Example 1: Test configuration for the local computer</span></span>

```
PS C:\> Test-DscConfiguration
```

<span data-ttu-id="bcc34-121">Эта команда проверяет конфигурацию для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bcc34-121">This command tests configuration for the local computer.</span></span>

### <span data-ttu-id="bcc34-122">Пример 2. Конфигурация теста для указанного компьютера</span><span class="sxs-lookup"><span data-stu-id="bcc34-122">Example 2: Test configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

<span data-ttu-id="bcc34-123">В этом примере проверяется конфигурация компьютера, указанного сеансом CIM.</span><span class="sxs-lookup"><span data-stu-id="bcc34-123">This example test configuration from a computer specified by a CIM session.</span></span>
<span data-ttu-id="bcc34-124">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="bcc34-124">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="bcc34-125">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="bcc34-125">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="bcc34-126">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="bcc34-126">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="bcc34-127">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="bcc34-127">The command prompts you for a password.</span></span>
<span data-ttu-id="bcc34-128">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="bcc34-128">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="bcc34-129">Вторая команда проверяет конфигурацию компьютеров, определенных объектами **CimSession** , сохраненными в переменной $Session, в данном случае — для компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="bcc34-129">The second command tests configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

### <span data-ttu-id="bcc34-130">Пример 3. тестовые конфигурации с подробными результатами</span><span class="sxs-lookup"><span data-stu-id="bcc34-130">Example 3: Test configurations with detailed results</span></span>

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

<span data-ttu-id="bcc34-131">Эта команда проверяет конфигурации для набора компьютеров, указанных параметром *ComputerName* , и возвращает подробные сведения, включающие в себя общее состояние, ресурсы, которые находятся в нужном состоянии, ресурсы, которые не находятся в нужном состоянии и имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="bcc34-131">This command tests configurations for a set of computers specified by the *ComputerName* parameter and returns detailed information that includes the overall state, resources that are in the desired state, resources that are not in the desired state and computer name.</span></span>

### <span data-ttu-id="bcc34-132">Пример 4. конфигурации тестов, указанные в папке</span><span class="sxs-lookup"><span data-stu-id="bcc34-132">Example 4: Test configurations specified in a folder</span></span>

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

<span data-ttu-id="bcc34-133">Эта команда проверяет конфигурации, определенные в папке, указанной параметром *path* .</span><span class="sxs-lookup"><span data-stu-id="bcc34-133">This command tests configurations that are defined in a folder specified by the *Path* parameter.</span></span>
<span data-ttu-id="bcc34-134">Конфигурации проверяются на наборе компьютеров, каждый из которых определяется по имени файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcc34-134">The configurations are tested against a set of computers, each identified by the file name of the configuration file.</span></span>

### <span data-ttu-id="bcc34-135">Пример 5. конфигурации тестов, указанные в файле</span><span class="sxs-lookup"><span data-stu-id="bcc34-135">Example 5: Test configurations specified in a file</span></span>

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

<span data-ttu-id="bcc34-136">Эта команда проверяет конфигурацию, определенную в файле, по набору компьютеров, заданному параметром *ComputerName* .</span><span class="sxs-lookup"><span data-stu-id="bcc34-136">This command tests a configuration defined in a file against a set of computers specified by the *ComputerName* parameter.</span></span>

## <span data-ttu-id="bcc34-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bcc34-137">PARAMETERS</span></span>

### <span data-ttu-id="bcc34-138">-AsJob</span><span class="sxs-lookup"><span data-stu-id="bcc34-138">-AsJob</span></span>
<span data-ttu-id="bcc34-139">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bcc34-139">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="bcc34-140">Если указать параметр *AsJob* , команда возвращает объект, представляющий задание, а затем появляется командная строка.</span><span class="sxs-lookup"><span data-stu-id="bcc34-140">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="bcc34-141">Вы можете продолжить работу в рамках данного сеанса, пока задание не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="bcc34-141">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="bcc34-142">Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bcc34-142">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="bcc34-143">Для управления заданием используйте командлеты Job.</span><span class="sxs-lookup"><span data-stu-id="bcc34-143">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="bcc34-144">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="bcc34-144">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="bcc34-145">Чтобы использовать этот параметр, локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия, а в Windows Vista и более поздних версиях операционной системы Windows необходимо также запустить Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="bcc34-145">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="bcc34-146">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcc34-146">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="bcc34-147">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bcc34-147">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-148">-CimSession</span><span class="sxs-lookup"><span data-stu-id="bcc34-148">-CimSession</span></span>
<span data-ttu-id="bcc34-149">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bcc34-149">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="bcc34-150">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="bcc34-150">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="bcc34-151">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bcc34-151">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="bcc34-152">-ComputerName</span></span>
<span data-ttu-id="bcc34-153">Указывает массив имен компьютеров, на которых этот командлет проверяет конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bcc34-153">Specifies an array of computer names on which this cmdlet tests the configuration.</span></span>
<span data-ttu-id="bcc34-154">Командлет проверяет документ конфигурации в расположении, указанном параметром *path* , для этих компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bcc34-154">The cmdlet tests the configuration document in the location specified by the *Path* parameter to these computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="bcc34-155">-Credential</span></span>
<span data-ttu-id="bcc34-156">Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="bcc34-156">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="bcc34-157">Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="bcc34-157">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="bcc34-158">Для получения дополнительных сведений введите `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="bcc34-158">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-159">-Detailed</span><span class="sxs-lookup"><span data-stu-id="bcc34-159">-Detailed</span></span>
<span data-ttu-id="bcc34-160">Указывает, что этот командлет возвращает подробный результат сравнения документа конфигурации с требуемым состоянием узлов.</span><span class="sxs-lookup"><span data-stu-id="bcc34-160">Indicates that this cmdlet returns a detailed result of comparing the configuration document with the desired state of the nodes.</span></span>
<span data-ttu-id="bcc34-161">Результат включает такие сведения, как общее состояние, ресурсы, которые находятся в требуемом состоянии, ресурсы, которые не находятся в требуемом состоянии, и имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="bcc34-161">The result includes information such as overall state, resources that are in the desired state, resources that are not in desired state, and computer name.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-162">-Path</span><span class="sxs-lookup"><span data-stu-id="bcc34-162">-Path</span></span>
<span data-ttu-id="bcc34-163">Указывает путь к папке, содержащей файлы документов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcc34-163">Specifies the path of a folder that contains configuration document files.</span></span>
<span data-ttu-id="bcc34-164">Командлет проверяет конфигурацию на соответствие требуемому состоянию компьютеров, указанных параметром *ComputerName* или *CimSession* .</span><span class="sxs-lookup"><span data-stu-id="bcc34-164">The cmdlet tests the configuration against the desired state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-165">-Референцеконфигуратион</span><span class="sxs-lookup"><span data-stu-id="bcc34-165">-ReferenceConfiguration</span></span>
<span data-ttu-id="bcc34-166">Указывает путь к файлу документа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcc34-166">Specifies the path of the configuration document file.</span></span>
<span data-ttu-id="bcc34-167">Этот командлет проверяет конфигурацию на соответствие фактическому состоянию компьютеров, указанных параметром *ComputerName* или *CimSession* .</span><span class="sxs-lookup"><span data-stu-id="bcc34-167">This cmdlet tests the configuration against the actual state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-168">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="bcc34-168">-ThrottleLimit</span></span>
<span data-ttu-id="bcc34-169">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="bcc34-169">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="bcc34-170">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bcc34-170">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="bcc34-171">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="bcc34-171">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc34-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bcc34-172">CommonParameters</span></span>
<span data-ttu-id="bcc34-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bcc34-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bcc34-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bcc34-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bcc34-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bcc34-175">INPUTS</span></span>

## <span data-ttu-id="bcc34-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bcc34-176">OUTPUTS</span></span>

## <span data-ttu-id="bcc34-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bcc34-177">NOTES</span></span>

## <span data-ttu-id="bcc34-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bcc34-178">RELATED LINKS</span></span>

[<span data-ttu-id="bcc34-179">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="bcc34-179">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="bcc34-180">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bcc34-180">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="bcc34-181">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="bcc34-181">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="bcc34-182">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bcc34-182">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="bcc34-183">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bcc34-183">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)
