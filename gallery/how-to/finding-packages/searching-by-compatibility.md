---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: коллекции,powershell,командлет,psgallery
title: Пакеты с совместимыми выпусками PowerShell или операционной системы
ms.openlocfilehash: 8230866561d3021379a48cc2c83fb4104a4058c1
ms.sourcegitcommit: d396d0e4cfe3d279f399c17e7337380a31d373ac
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2018
ms.locfileid: "53747710"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a>Пакеты с совместимыми выпусками PowerShell или операционных систем

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

## <a name="searching-by-powershell-edition"></a>Поиск по выпуску PowerShell 
В двух версиях Powershell являются:
- Desktop Edition На платформе .NET Framework и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в полноценных выпусках Windows, такие как ядро сервера и Windows Desktop.
- **Выпуск Core:** Опирается на .NET Core и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в сокращенных выпусках Windows, таких как Nano Server и Windows IoT.

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a>Коллекция PowerShell позволяет фильтровать пакеты совместимы конкретными выпусками PowerShell

Если пакет содержит совместимых PSEditions указаны, они перечислены как часть «Выпуски PowerShell» в отображаемой страницы пакета, а также в результатах пакетов.
Кроме того, можно выполнять поиск совместимых пакетов, с помощью PowerShell.

![Страница отображения элемента с выпусками PSEdition](../../Images/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a>Поиск пакетов в коллекции пользовательского интерфейса, которые работают в PowerShell Core

Для фильтрации пакетов в коллекции PowerShell используйте Tags:"PSEdition_Desktop" и Tags:"PSEdition_Core".

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Core, используйте Tags:"PSEdition_Core".

![Результаты поиска элементов, совместимых с Core PSEdition](../../Images/searchresultswithpseditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Для поиска элементов, совместимых с выпуском PowerShell Desktop, используйте Tags:"PSEdition_Desktop".

![Результаты поиска элементов, совместимых с Desktop PSEdition](../../Images/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a>Поиск пакетов найти совместимыми выпусками с помощью PowerShell
Можно указать теги для фильтрации версии PowerShell и операционной системы. Использовании `Find-Package` указание командлет `-Tag` параметр, чтобы указать выпуск (и ОС) вы используете.
Типа того:

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a>Поиск по операционной системы 

Так как PowerShell Core будет доступен для Windows, Linux и MacOS, пакеты в коллекции может обеспечивать любое сочетание этих операционных систем. В коллекции пользовательского интерфейса с помощью следующих тегов searchs для поиска пакетов, отмеченному поведением операционной системы:

- Теги: "Windows"
- Теги: "Linux"
- Теги: "MacOS" 

Эти теги можно указать на `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a>Поиск нескольких совместимости

Можно найти пакет, который содержит несколько совместимости с помощью синтаксиса: 

Теги «Compatibility1» «Compatibility2» 

Например если вы ищете пакет с PowerShell Core совместимости, работающей на компьютерах моей Windows и Linux, используйте поиск тегов:

Теги «PSEdition_Core», «Windows», «Linux» 

Чтобы выполнить поиск с помощью PowerShell, можно использовать `Find-Module` (и другие командлеты в модуле PowerShellGet) следующим образом:

```powewrshell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a>Дополнительные сведения о разработке и поиске пакетов с совместимыми выпусками PowerShell

- [Модули с PSEditions](../../concepts/module-psedition-support.md)
- [Скрипты с PSEdition](../../concepts/script-psedition-support.md)
