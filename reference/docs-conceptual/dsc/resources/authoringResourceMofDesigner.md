---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Использование конструктора ресурсов
ms.openlocfilehash: 36eed0fc888380a03a3279e834748708f578d973
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500626"
---
# <a name="using-the-resource-designer-tool"></a><span data-ttu-id="cbe19-103">Использование конструктора ресурсов</span><span class="sxs-lookup"><span data-stu-id="cbe19-103">Using the Resource Designer tool</span></span>

> <span data-ttu-id="cbe19-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="cbe19-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="cbe19-105">Конструктор ресурсов — это набор командлетов, предоставляемых модулем **xDscResourceDesigner** и упрощающих создание ресурсов настройки требуемого состояния (DSC) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbe19-105">The Resource Designer tool is a set of cmdlets exposed by the **xDscResourceDesigner** module that make creating Windows PowerShell Desired State Configuration (DSC) resources easier.</span></span> <span data-ttu-id="cbe19-106">Командлеты в этом ресурсе помогают создать MOF-схему, модуль сценария и структуру папок для нового ресурса.</span><span class="sxs-lookup"><span data-stu-id="cbe19-106">The cmdlets in this resource help create the MOF schema, the script module, and the directory structure for your new resource.</span></span> <span data-ttu-id="cbe19-107">Дополнительные сведения о ресурсах DSC см. в статье [Встроенные ресурсы настройки требуемого состояния (DSC) Windows PowerShell](authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="cbe19-107">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md).</span></span> <span data-ttu-id="cbe19-108">В этом разделе мы создадим ресурс DSC, управляющий пользователями Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cbe19-108">In this topic, we will create a DSC resource that manages Active Directory users.</span></span> <span data-ttu-id="cbe19-109">Для установки модуля **xDscResourceDesigner** используйте командлет [Install-Module](/powershell/module/PowershellGet/Install-Module).</span><span class="sxs-lookup"><span data-stu-id="cbe19-109">Use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xDscResourceDesigner** module.</span></span>

## <a name="creating-resource-properties"></a><span data-ttu-id="cbe19-110">Создание свойств ресурсов</span><span class="sxs-lookup"><span data-stu-id="cbe19-110">Creating resource properties</span></span>
<span data-ttu-id="cbe19-111">В первую очередь необходимо решить, какие свойства будут представлены в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="cbe19-111">The first thing we need to do is decide on properties that the resource will expose.</span></span> <span data-ttu-id="cbe19-112">В этом примере мы определим пользователя Active Directory со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="cbe19-112">For this example, we will define an Active Directory user with the following properties.</span></span>

<span data-ttu-id="cbe19-113">Имя параметра Описание</span><span class="sxs-lookup"><span data-stu-id="cbe19-113">Parameter name  Description</span></span>
* <span data-ttu-id="cbe19-114">**UserName**: основное свойство, которое служит уникальным идентификатором пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbe19-114">**UserName**: Key property that uniquely identifies a user.</span></span>
* <span data-ttu-id="cbe19-115">**Ensure**: указывает, должна ли учетная запись пользователя присутствовать (Present) или отсутствовать (Absent).</span><span class="sxs-lookup"><span data-stu-id="cbe19-115">**Ensure**: Specifies whether the user account should be Present or Absent.</span></span> <span data-ttu-id="cbe19-116">Этот параметр имеет только два возможных значения.</span><span class="sxs-lookup"><span data-stu-id="cbe19-116">This parameter will have only two possible values.</span></span>
* <span data-ttu-id="cbe19-117">**DomainCredential**: доменный пароль для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbe19-117">**DomainCredential**: The domain password for the user.</span></span>
* <span data-ttu-id="cbe19-118">**Password**: пароль для пользователя, позволяющий конфигурации при необходимости изменить пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbe19-118">**Password**: The desired password for the user to allow a configuration to change the user password if necessary.</span></span>

<span data-ttu-id="cbe19-119">Для создания свойств используется командлет **New-xDscResourceProperty**.</span><span class="sxs-lookup"><span data-stu-id="cbe19-119">To create the properties, we use the **New-xDscResourceProperty** cmdlet.</span></span> <span data-ttu-id="cbe19-120">Описанные выше свойства создаются следующими командами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbe19-120">The following PowerShell commands create the properties described above.</span></span>

```powershell
$UserName = New-xDscResourceProperty –Name UserName -Type String -Attribute Key
$Ensure = New-xDscResourceProperty –Name Ensure -Type String -Attribute Write –ValidateSet "Present", "Absent"
$DomainCredential = New-xDscResourceProperty –Name DomainCredential -Type PSCredential -Attribute Write
$Password = New-xDscResourceProperty –Name Password -Type PSCredential -Attribute Write
```

## <a name="create-the-resource"></a><span data-ttu-id="cbe19-121">Создание ресурса</span><span class="sxs-lookup"><span data-stu-id="cbe19-121">Create the resource</span></span>

<span data-ttu-id="cbe19-122">Теперь, когда свойства ресурса созданы, можно вызвать командлет **New-xDscResource** для создания ресурса.</span><span class="sxs-lookup"><span data-stu-id="cbe19-122">Now that the resource properties have been created, we can call the **New-xDscResource** cmdlet to create the resource.</span></span> <span data-ttu-id="cbe19-123">Командлет **New-xDscResource** выводит список свойств в виде параметров.</span><span class="sxs-lookup"><span data-stu-id="cbe19-123">The **New-xDscResource** cmdlet takes the list of properties as parameters.</span></span> <span data-ttu-id="cbe19-124">Кроме того, он принимает путь для создания модуля, имя нового ресурса и имя модуля, в котором он будет храниться.</span><span class="sxs-lookup"><span data-stu-id="cbe19-124">It also takes the path where the module should be created, the name of the new resource, and the name of the module in which it is contained.</span></span> <span data-ttu-id="cbe19-125">Ресурс создает следующая команда PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbe19-125">The following PowerShell command creates the resource.</span></span>

```powershell
New-xDscResource –Name Demo_ADUser –Property $UserName, $Ensure, $DomainCredential, $Password –Path 'C:\Program Files\WindowsPowerShell\Modules' –ModuleName Demo_DSCModule
```

<span data-ttu-id="cbe19-126">Командлет **New-xDscResource** создает MOF-схему, каркас сценария для ресурса, необходимую структуру папок, а также манифест для модуля, предоставляющего новый ресурс.</span><span class="sxs-lookup"><span data-stu-id="cbe19-126">The **New-xDscResource** cmdlet creates the MOF schema, a skeleton resource script, the required directory structure for your new resource, and a manifest for the module that exposes the new resource.</span></span>

<span data-ttu-id="cbe19-127">MOF-схема находится в файле **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof** и имеет следующее содержание:</span><span class="sxs-lookup"><span data-stu-id="cbe19-127">The MOF schema file is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof**, and its contents are as follows.</span></span>

```
[ClassVersion("1.0.0.0"), FriendlyName("Demo_ADUser")]
class Demo_ADUser : OMI_BaseResource
{
  [Key] string UserName;
  [Write, ValueMap{"Present","Absent"}, Values{"Present","Absent"}] string Ensure;
  [Write, EmbeddedInstance("MSFT_Credential")] String DomainCredential;
  [Write, EmbeddedInstance("MSFT_Credential")] String Password;
};
```

<span data-ttu-id="cbe19-128">Сценарий ресурса находится в файле **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1**.</span><span class="sxs-lookup"><span data-stu-id="cbe19-128">The resource script is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1**.</span></span>
<span data-ttu-id="cbe19-129">Он не содержит фактической логики реализации ресурса — ее необходимо добавить самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="cbe19-129">It does not include the actual logic to implement the resource, which you must add yourself.</span></span> <span data-ttu-id="cbe19-130">Каркас сценария выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cbe19-130">The contents of the skeleton script are as follows.</span></span>

```powershell
function Get-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Collections.Hashtable])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $returnValue = @{
  UserName = [System.String]
  Ensure = [System.String]
  DomainAdminCredential = [System.Management.Automation.PSCredential]
  Password = [System.Management.Automation.PSCredential]
  }

  $returnValue
  #>
}


function Set-TargetResource
{
  [CmdletBinding()]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  #Include this line if the resource requires a system reboot.
  #$global:DSCMachineStatus = 1


}


function Test-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Boolean])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $result = [System.Boolean]

  $result
  #>
}


Export-ModuleMember -Function *-TargetResource
```

## <a name="updating-the-resource"></a><span data-ttu-id="cbe19-131">Обновление ресурса</span><span class="sxs-lookup"><span data-stu-id="cbe19-131">Updating the resource</span></span>

<span data-ttu-id="cbe19-132">Если вам нужно добавить или изменить список параметров для ресурса, используйте командлет **Update-xDscResource**.</span><span class="sxs-lookup"><span data-stu-id="cbe19-132">If you need to add or modify the parameter list of the resource, you can call the **Update-xDscResource** cmdlet.</span></span> <span data-ttu-id="cbe19-133">Этот командлет обновляет ресурс с учетом нового списка параметров.</span><span class="sxs-lookup"><span data-stu-id="cbe19-133">The cmdlet updates the resource with a new parameter list.</span></span> <span data-ttu-id="cbe19-134">Если логика в сценарий ресурсов уже добавлена, она останется без изменений.</span><span class="sxs-lookup"><span data-stu-id="cbe19-134">If you have already added logic in your resource script, it is left intact.</span></span>

<span data-ttu-id="cbe19-135">Предположим, вам нужно включить в ресурс время последнего входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbe19-135">For example, suppose you want to include the last log in time for the user in our resource.</span></span> <span data-ttu-id="cbe19-136">Вместо того чтобы писать ресурс заново, можно выполнить командлет **New-xDscResourceProperty**, чтобы создать еще одно свойство, а затем командлет **Update-xDscResource**, чтобы добавить его в список свойств.</span><span class="sxs-lookup"><span data-stu-id="cbe19-136">Rather than writing the resource again completely, you can call the **New-xDscResourceProperty** to create the new property, and then call **Update-xDscResource** and add your new property to the properties list.</span></span>

```powershell
$lastLogon = New-xDscResourceProperty –Name LastLogon –Type Hashtable –Attribute Write –Description "For mapping users to their last log on time"
Update-xDscResource –Name 'Demo_ADUser' –Property $UserName, $Ensure, $DomainCredential, $Password, $lastLogon -Force
```

## <a name="testing-a-resource-schema"></a><span data-ttu-id="cbe19-137">Тестирование схемы ресурсов</span><span class="sxs-lookup"><span data-stu-id="cbe19-137">Testing a resource schema</span></span>

<span data-ttu-id="cbe19-138">Конструктор ресурсов предоставляет еще один командлет, который можно использовать для проверки работоспособности MOF-схемы, написанной вами вручную.</span><span class="sxs-lookup"><span data-stu-id="cbe19-138">The Resource Designer tool exposes one more cmdlet that can be used to test the validity of a MOF schema that you have written manually.</span></span> <span data-ttu-id="cbe19-139">Вызовите командлет **Test-xDscSchema**, передав в качестве параметра путь к MOF-схеме ресурса.</span><span class="sxs-lookup"><span data-stu-id="cbe19-139">Call the **Test-xDscSchema** cmdlet, passing the path of a MOF resource schema as a parameter.</span></span> <span data-ttu-id="cbe19-140">Командлет выдаст все имеющиеся в схеме ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbe19-140">The cmdlet will output any errors in the schema.</span></span>

### <a name="see-also"></a><span data-ttu-id="cbe19-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbe19-141">See Also</span></span>

#### <a name="concepts"></a><span data-ttu-id="cbe19-142">Основные понятия</span><span class="sxs-lookup"><span data-stu-id="cbe19-142">Concepts</span></span>
[<span data-ttu-id="cbe19-143">Создание пользовательских ресурсов DSC Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbe19-143">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)

#### <a name="other-resources"></a><span data-ttu-id="cbe19-144">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="cbe19-144">Other Resources</span></span>
[<span data-ttu-id="cbe19-145">Модуль xDscResourceDesigner</span><span class="sxs-lookup"><span data-stu-id="cbe19-145">xDscResourceDesigner Module</span></span>](https://www.powershellgallery.com/packages/xDscResourceDesigner/1.12.0.0)
