---
ms.date: 06/09/2017
title: Запрос на принятие условий лицензии для сценариев
description: В этой статье описывается, как работать со скриптами, опубликованными в коллекции PowerShell, которые требуют принятия лицензии пользователя.
ms.openlocfilehash: d82974810fd1e73ef8d9e5771fc430d0f7964e87
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656087"
---
# <a name="requiring-license-acceptance-for-scripts"></a><span data-ttu-id="28205-103">Запрос на принятие условий лицензии для сценариев</span><span class="sxs-lookup"><span data-stu-id="28205-103">Requiring license acceptance for scripts</span></span>

<span data-ttu-id="28205-104">Для скриптов процедура принятия условий лицензионного соглашения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="28205-104">License Acceptance is not supported for scripts.</span></span> <span data-ttu-id="28205-105">Но поддерживается вариант, при котором скрипт зависит от модуля, для использования которого требуется принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="28205-105">However, the scenario where a script depends on a module that requires license acceptance is supported.</span></span>

<span data-ttu-id="28205-106">Команды скрипта PowerShellGet поддерживают параметр **AcceptLicense** , поведение которого аналогично поведению при принятии пользователем лицензии.</span><span class="sxs-lookup"><span data-stu-id="28205-106">The PowerShellGet script commands support the parameter **AcceptLicense** that behaves as though user saw the license.</span></span> <span data-ttu-id="28205-107">Если параметр **AcceptLicense** не указан, пользователю отображается файл `license.txt` для зависимого модуля и выводится запрос на принятие лицензии.</span><span class="sxs-lookup"><span data-stu-id="28205-107">If **AcceptLicense** is not specified the user is shown the `license.txt` file for dependent module and prompted to accept the license.</span></span>

## <a name="examples"></a><span data-ttu-id="28205-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="28205-108">EXAMPLES</span></span>

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="28205-109">Пример 1. Установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения</span><span class="sxs-lookup"><span data-stu-id="28205-109">Example 1: Install Script with dependencies requiring license acceptance</span></span>

<span data-ttu-id="28205-110">Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance.</span><span class="sxs-lookup"><span data-stu-id="28205-110">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="28205-111">Пользователю предлагается принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="28205-111">User is prompted to Accept License.</span></span>

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="28205-112">Пример 2. Установка скрипта с зависимостями, для использования которого требуется принять условия лицензионного соглашения и указать -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="28205-112">Example 2: Install Script with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="28205-113">Скрипт ScriptRequireLicenseAcceptance зависит от модуля ModuleRequireLicenseAcceptance.</span><span class="sxs-lookup"><span data-stu-id="28205-113">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="28205-114">Пользователю не предлагается принять условия лицензии, так как указан параметр -AcceptLicense.</span><span class="sxs-lookup"><span data-stu-id="28205-114">User is not prompted to accept license as -AcceptLicense is specified.</span></span>

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a><span data-ttu-id="28205-115">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="28205-115">More details</span></span>

- [<span data-ttu-id="28205-116">Поддержка запроса на принятие условий лицензионного соглашения для модулей</span><span class="sxs-lookup"><span data-stu-id="28205-116">Require License Acceptance support for Modules</span></span>](module-license-acceptance.md)
- [<span data-ttu-id="28205-117">Поддержка запроса на принятие условий лицензионного соглашения в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="28205-117">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [<span data-ttu-id="28205-118">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="28205-118">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
