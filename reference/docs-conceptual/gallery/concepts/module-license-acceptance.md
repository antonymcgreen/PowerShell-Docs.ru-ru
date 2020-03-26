---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: Модули, для использования которых требуется принять условия лицензии
ms.openlocfilehash: a2f7ed72aae8579a6723f65b86dd0993f1a22afd
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082811"
---
# <a name="modules-requiring-license-acceptance"></a><span data-ttu-id="ff526-103">Модули, для использования которых требуется принять условия лицензии</span><span class="sxs-lookup"><span data-stu-id="ff526-103">Modules Requiring License Acceptance</span></span>

## <a name="synopsis"></a><span data-ttu-id="ff526-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ff526-104">SYNOPSIS</span></span>

<span data-ttu-id="ff526-105">В юридических требованиях некоторых издателей модулей указано, что перед установкой модуля из коллекции PowerShell пользователи должны явным образом принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-105">Legal departments for some module publishers require that customers must explicitly accept the license before installing their module from PowerShell Gallery.</span></span> <span data-ttu-id="ff526-106">Если пользователь устанавливает, обновляет или сохраняет такой модуль с помощью PowerShellGet (непосредственно или как зависимость для другого пакета), он должен указать, что принимает такие условия. Иначе операция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ff526-106">If a user installs, updates, or saves a module using PowerShellGet, whether directly or as a dependency for another package, and that module requires the user to agree to a license, the user must indicate they accept the license or the operation fails.</span></span>

## <a name="publish-requirements-for-modules"></a><span data-ttu-id="ff526-107">Требования к публикации модулей</span><span class="sxs-lookup"><span data-stu-id="ff526-107">Publish Requirements for Modules</span></span>

<span data-ttu-id="ff526-108">Модули, для использования которых нужно принять условия лицензионного соглашения, должны соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="ff526-108">Modules that would like to require users to accept license should fulfill following requirements:</span></span>

- <span data-ttu-id="ff526-109">В разделе PSData манифеста модуля для параметра RequireLicenseAcceptance должно быть установлено значение $True.</span><span class="sxs-lookup"><span data-stu-id="ff526-109">PSData section of module manifest should include RequireLicenseAcceptance = $True.</span></span>
- <span data-ttu-id="ff526-110">В корневом каталоге модуля должен содержаться файл license.txt.</span><span class="sxs-lookup"><span data-stu-id="ff526-110">Module should contain license.txt file in root directory.</span></span>
- <span data-ttu-id="ff526-111">Манифест модуля должен содержать URI лицензии.</span><span class="sxs-lookup"><span data-stu-id="ff526-111">Module manifest should contain License Uri.</span></span>
- <span data-ttu-id="ff526-112">Модуль должен быть опубликован в формате PowerShellGet 2.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ff526-112">Module should be published with PowerShellGet Format Version 2.0 and above.</span></span>

## <a name="impact-on-installsaveupdate-module"></a><span data-ttu-id="ff526-113">Влияние на командлеты Install/Save/Update-Module</span><span class="sxs-lookup"><span data-stu-id="ff526-113">Impact on Install/Save/Update-Module</span></span>

- <span data-ttu-id="ff526-114">Командлеты установки, сохранения и обновления поддерживают новый параметр **AcceptLicense**. Его поведение аналогично действиям пользователя после прочтения лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-114">Install/Save/Update cmdlets support a new parameter **AcceptLicense** that behaves as though the user saw the license.</span></span>
- <span data-ttu-id="ff526-115">Если для параметра **RequiredLicenseAcceptance** установлено значение True, а параметр **AcceptLicense** не указан, для пользователя будет отображаться файл `license.txt` и запрос: `Do you accept these license terms
  (Yes/No/YesToAll/NoToAll)`.</span><span class="sxs-lookup"><span data-stu-id="ff526-115">If **RequiredLicenseAcceptance** is True and **AcceptLicense** is not specified, the user is shown the `license.txt`, and prompted with: `Do you accept these license terms
  (Yes/No/YesToAll/NoToAll)`.</span></span>
  - <span data-ttu-id="ff526-116">Если условия лицензионного соглашения принимаются:</span><span class="sxs-lookup"><span data-stu-id="ff526-116">If the license is accepted</span></span>
    - <span data-ttu-id="ff526-117">**Save-Module**: модуль копируется в систему пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff526-117">**Save-Module:** the module is copied to the user's system</span></span>
    - <span data-ttu-id="ff526-118">**Install-Module**: модуль копируется в надлежащую папку в системе пользователя (в зависимости от области действия).</span><span class="sxs-lookup"><span data-stu-id="ff526-118">**Install-Module:** the module is copied to the user's system to the proper folder (based on scope)</span></span>
    - <span data-ttu-id="ff526-119">**Update-Module**: модуль обновляется.</span><span class="sxs-lookup"><span data-stu-id="ff526-119">**Update-Module:** the module is updated.</span></span>
  - <span data-ttu-id="ff526-120">Если условия лицензионного соглашения отклоняются:</span><span class="sxs-lookup"><span data-stu-id="ff526-120">If the license is declined.</span></span>
    - <span data-ttu-id="ff526-121">Операция отменяется.</span><span class="sxs-lookup"><span data-stu-id="ff526-121">Operation is canceled.</span></span>
    - <span data-ttu-id="ff526-122">Все командлеты проверяют метаданные (**requireLicenseAcceptance** и версию формата), которые свидетельствуют о том, что требуется принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-122">All cmdlets check for the metadata (**requireLicenseAcceptance** and Format Version) that says a license acceptance is required</span></span>
    - <span data-ttu-id="ff526-123">Если версия формата клиента более ранняя, чем 2.0, происходит сбой операции. Поступит запрос на обновление клиента.</span><span class="sxs-lookup"><span data-stu-id="ff526-123">If format version of client is older than 2.0, operation fails and asks the user to update the client.</span></span>
    - <span data-ttu-id="ff526-124">Если модуль опубликован с версией формата более ранней, чем 2.0, флаг requireLicenseAcceptance игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ff526-124">If module was published with format version older than 2.0, requireLicenseAcceptance flag is ignored.</span></span>

## <a name="module-dependencies"></a><span data-ttu-id="ff526-125">Зависимости модулей</span><span class="sxs-lookup"><span data-stu-id="ff526-125">Module Dependencies</span></span>

- <span data-ttu-id="ff526-126">Если при установке, сохранении или обновлении зависимого модуля (или зависимостей модуля) требуется принять условия лицензионного соглашения, необходимо настроить поведение принятия лицензии (процедура описана выше).</span><span class="sxs-lookup"><span data-stu-id="ff526-126">During Install/Save/Update operation, if a dependent module(something else depends on the module) requires license acceptance, then the license acceptance behavior (above) is required.</span></span>
- <span data-ttu-id="ff526-127">Если версия модуля уже указана в локальном каталоге как установленная в системе, пропустите процедуру проверки лицензии.</span><span class="sxs-lookup"><span data-stu-id="ff526-127">If the module version is already listed in the local catalog as being installed on the system, we would bypass the license checking.</span></span>
- <span data-ttu-id="ff526-128">Если при установке, сохранении или обновлении зависимого модуля требуется принять условия лицензионного соглашения, но они не принимаются, происходит сбой операции. Будут выполняться стандартные процессы, сопровождающие ошибку установки, сохранения или обновления пакета.</span><span class="sxs-lookup"><span data-stu-id="ff526-128">During Install/Save/Update operation, if a dependent module requires a license, and the license acceptance does not occur, the operation fails and follows normal processes for the package failed to install/save/update.</span></span>

## <a name="impact-on--force"></a><span data-ttu-id="ff526-129">Влияние на параметр -Force</span><span class="sxs-lookup"><span data-stu-id="ff526-129">Impact on -Force</span></span>

<span data-ttu-id="ff526-130">Указание `–Force` НЕ является достаточным для принятия условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-130">Specifying `–Force` is NOT sufficient to accept a license.</span></span> <span data-ttu-id="ff526-131">Для разрешения на установку требуется указать `–AcceptLicense`.</span><span class="sxs-lookup"><span data-stu-id="ff526-131">`–AcceptLicense` is required for permission to install.</span></span> <span data-ttu-id="ff526-132">Если указан параметр `–Force`, для RequiredLicenseAcceptance установлено значение True, а параметр `–AcceptLicense` НЕ указан, происходит сбой операции.</span><span class="sxs-lookup"><span data-stu-id="ff526-132">If `–Force` is specified, RequiredLicenseAcceptance is True, and `–AcceptLicense` is NOT specified, the operation fails.</span></span>

## <a name="examples"></a><span data-ttu-id="ff526-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="ff526-133">EXAMPLES</span></span>

### <a name="example-1-update-module-manifest-to-require-license-acceptance"></a><span data-ttu-id="ff526-134">Пример 1: обновление манифеста модуля для запроса на принятие условий лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ff526-134">Example 1: Update Module Manifest to require license acceptance</span></span>

```powershell
Update-ModuleManifest -Path C:\modulemanifest.psd1 -RequireLicenseAcceptance -PrivateData @{
    PSData = @{
        # Flag to indicate whether the module requires explicit user acceptance
        RequireLicenseAcceptance = $true
    } # End of PSData hashtable

 } # End of PrivateData hashtable
```

<span data-ttu-id="ff526-135">Эта команда позволяет обновить файл манифеста и установить для флага RequireLicenseAcceptance значение true.</span><span class="sxs-lookup"><span data-stu-id="ff526-135">This command updates the manifest file and sets the RequireLicenseAcceptance flag to true.</span></span>

### <a name="example-2-install-module-requiring-license-acceptance"></a><span data-ttu-id="ff526-136">Пример 2. Установка модуля, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ff526-136">Example 2: Install Module requiring license acceptance</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ff526-137">Эта команда предназначена для отображения лицензии файла `license.txt` и запроса на принятие условий лицензионного соглашения пользователем.</span><span class="sxs-lookup"><span data-stu-id="ff526-137">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-3-install-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="ff526-138">Пример 3. Установка модуля, для использования которого требуется принять условия лицензионного соглашения, при помощи -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ff526-138">Example 3: Install Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="ff526-139">Модуль устанавливается без запросов на принятие условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-139">Module is installed without any prompt to accept license.</span></span>

### <a name="example-4-install-module-requiring-license-acceptance-with--force"></a><span data-ttu-id="ff526-140">Пример 4. Установка модуля, для использования которого требуется принять условия лицензионного соглашения при помощи -Force</span><span class="sxs-lookup"><span data-stu-id="ff526-140">Example 4: Install Module requiring license acceptance with -Force</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance -Force
```

```Output
PackageManagement\Install-Package : License Acceptance is required for module 'ModuleRequireLicenseAcceptance'. Please specify '-AcceptLicense' to perform this operation.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.1.3.3\PSModule.psm1:1837 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], E
   xception
    + FullyQualifiedErrorId : ForceAcceptLicense,Install-PackageUtility,Microsoft.PowerShell.PackageManagement.Cmdlets
   .InstallPackage
```

### <a name="example-5-install-module-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="ff526-141">Пример 5. Установка модуля с зависимостями, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ff526-141">Example 5: Install Module with dependencies requiring license acceptance</span></span>

<span data-ttu-id="ff526-142">Модуль **ModuleWithDependency** зависит от модуля **ModuleRequireLicenseAcceptance**.</span><span class="sxs-lookup"><span data-stu-id="ff526-142">Module **ModuleWithDependency** depends on module **ModuleRequireLicenseAcceptance**.</span></span> <span data-ttu-id="ff526-143">Пользователю предлагается принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-143">User is prompted to accept license.</span></span>

```powershell
Install-Module -Name ModuleWithDependency
```

```Output
License Acceptance
MIT License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

### <a name="example-6-install-module-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="ff526-144">Пример 6. Установка модуля с зависимостями, для использования которого требуется принять условия лицензионного соглашения и указать -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ff526-144">Example 6: Install Module with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="ff526-145">Модуль **ModuleWithDependency** зависит от модуля **ModuleRequireLicenseAcceptance**.</span><span class="sxs-lookup"><span data-stu-id="ff526-145">Module **ModuleWithDependency** depends on module **ModuleRequireLicenseAcceptance**.</span></span> <span data-ttu-id="ff526-146">Пользователю не предлагается принять условия лицензии, так как указан параметр **AcceptLicense**.</span><span class="sxs-lookup"><span data-stu-id="ff526-146">User is not prompted to accept license as **AcceptLicense** is specified.</span></span>

```powershell
Install-Module -Name ModuleWithDependency -AcceptLicense
```

### <a name="example-7-install-module-requiring-license-acceptance-on-a-client-older-than-psgetformatversion-20"></a><span data-ttu-id="ff526-147">Пример 7. Установка модуля, для использования которого требуется принять условия лицензионного соглашения, в клиенте с версией старше, чем PSGetFormatVersion 2.0</span><span class="sxs-lookup"><span data-stu-id="ff526-147">Example 7: Install module requiring license acceptance on a client older than PSGetFormatVersion 2.0</span></span>

```powershell
Install-Module -Name ModuleRequireLicenseAcceptance
```

```Output
WARNING: The specified module 'ModuleRequireLicenseAcceptance' with PowerShellGetFormatVersion
'2.0' is not supported by the current version of PowerShellGet. Get the latest version of the
PowerShellGet module to install this module, 'ModuleRequireLicenseAcceptance'.
```

### <a name="example-8-save-module-requiring-license-acceptance"></a><span data-ttu-id="ff526-148">Пример 8. Сохранение модуля, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ff526-148">Example 8: Save Module requiring license acceptance</span></span>

```powershell
Save-Module -Name ModuleRequireLicenseAcceptance -Path C:\Saved
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ff526-149">Эта команда предназначена для отображения лицензии файла `license.txt` и запроса на принятие условий лицензионного соглашения пользователем.</span><span class="sxs-lookup"><span data-stu-id="ff526-149">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-9-save-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="ff526-150">Пример 9. Сохранение модуля, для использования которого требуется принять условия лицензионного соглашения, при помощи -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ff526-150">Example 9: Save Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Save-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense -Path C:\Saved
```

<span data-ttu-id="ff526-151">Модуль сохраняется без запроса на принятие условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-151">Module is saved without any prompt to accept license.</span></span>

### <a name="example-10-update-module-requiring-license-acceptance"></a><span data-ttu-id="ff526-152">Пример 10. Обновление модуля, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ff526-152">Example 10: Update Module requiring license acceptance</span></span>

```powershell
Update-Module -Name ModuleRequireLicenseAcceptance
```

```Output
License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ff526-153">Эта команда предназначена для отображения лицензии файла `license.txt` и запроса на принятие условий лицензионного соглашения пользователем.</span><span class="sxs-lookup"><span data-stu-id="ff526-153">This command shows the license from `license.txt` file and prompts the user to accept the license.</span></span>

### <a name="example-11-update-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="ff526-154">Пример 11. Обновление модуля, для использования которого требуется принять условия лицензионного соглашения, при помощи -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ff526-154">Example 11: Update Module requiring license acceptance with -AcceptLicense</span></span>

```powershell
Update-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="ff526-155">Модуль обновляется без запроса на принятие условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff526-155">Module is updated without any prompt to accept license.</span></span>

## <a name="more-details"></a><span data-ttu-id="ff526-156">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ff526-156">More details</span></span>

[<span data-ttu-id="ff526-157">Запрос на принятие условий лицензии для скриптов</span><span class="sxs-lookup"><span data-stu-id="ff526-157">Require License Acceptance for Scripts</span></span>](./script-license-acceptance.md)

[<span data-ttu-id="ff526-158">Поддержка запроса на принятие условий лицензионного соглашения в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff526-158">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)

[<span data-ttu-id="ff526-159">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="ff526-159">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
