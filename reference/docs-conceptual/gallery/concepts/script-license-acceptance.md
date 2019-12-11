---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: Запрос на принятие условий лицензии для сценариев
ms.openlocfilehash: e7101eb6a480dd87965b7b9be9d49583042b603f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328085"
---
# <a name="requiring-license-acceptance-for-scripts"></a><span data-ttu-id="ecd60-103">Запрос на принятие условий лицензии для сценариев</span><span class="sxs-lookup"><span data-stu-id="ecd60-103">Requiring license acceptance for scripts</span></span>

<span data-ttu-id="ecd60-104">Для скриптов процедура принятия условий лицензионного соглашения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ecd60-104">License Acceptance is not supported for scripts.</span></span> <span data-ttu-id="ecd60-105">Но поддерживается вариант, при котором скрипт зависит от модуля, для использования которого требуется принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ecd60-105">However, the scenario where a script depends on a module that requires license acceptance is supported.</span></span>

<span data-ttu-id="ecd60-106">Команды скрипта (Install-Script/Save-Script/Update-Script) поддерживают новый параметр -AcceptLicense. Его поведение аналогично действиям пользователя после прочтения лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ecd60-106">Script commands(Install-Script/Save-Script/Update-Script) support a new parameter -AcceptLicense that behaves as though user saw the license.</span></span> <span data-ttu-id="ecd60-107">Если параметр -AcceptLicense не указан, для пользователя будет отображаться файл license.txt зависимого модуля и запрос на принятие условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ecd60-107">If -AcceptLicense is not specified; the user will be shown license.txt for dependent module and prompted to accept the license.</span></span>

## <a name="examples"></a><span data-ttu-id="ecd60-108">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="ecd60-108">EXAMPLES</span></span>

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="ecd60-109">Пример 1: установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="ecd60-109">Example 1: Install Script with dependencies requiring license acceptance</span></span>

<span data-ttu-id="ecd60-110">Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance.</span><span class="sxs-lookup"><span data-stu-id="ecd60-110">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="ecd60-111">Пользователю предлагается принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ecd60-111">User is prompted to Accept License.</span></span>

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="ecd60-112">Пример 2. Установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения и указать -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="ecd60-112">Example 2: Install Script with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="ecd60-113">Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance.</span><span class="sxs-lookup"><span data-stu-id="ecd60-113">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="ecd60-114">Пользователю не предлагается принять условия лицензии, так как указан параметр -AcceptLicense.</span><span class="sxs-lookup"><span data-stu-id="ecd60-114">User is not prompted to accept license as -AcceptLicense is specified.</span></span>

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a><span data-ttu-id="ecd60-115">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="ecd60-115">More details</span></span>

- [<span data-ttu-id="ecd60-116">Поддержка запроса на принятие условий лицензионного соглашения для модулей</span><span class="sxs-lookup"><span data-stu-id="ecd60-116">Require License Acceptance support for Modules</span></span>](module-license-acceptance.md)
- [<span data-ttu-id="ecd60-117">Поддержка запроса на принятие условий лицензионного соглашения в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecd60-117">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [<span data-ttu-id="ecd60-118">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="ecd60-118">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
