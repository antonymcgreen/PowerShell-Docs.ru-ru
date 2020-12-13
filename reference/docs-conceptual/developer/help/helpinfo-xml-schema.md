---
ms.date: 09/12/2016
ms.topic: reference
title: Схема XML-файла HelpInfo
description: Схема XML-файла HelpInfo
ms.openlocfilehash: 157fd9c0f47c57efbaa9b7888fa174a34ad9567d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662022"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="98791-103">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="98791-103">HelpInfo XML Schema</span></span>

<span data-ttu-id="98791-104">В этом разделе содержится схема XML для обновляемых файлов справки, которые обычно называются «HelpInfo XML Files».</span><span class="sxs-lookup"><span data-stu-id="98791-104">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="98791-105">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="98791-105">HelpInfo XML Schema</span></span>

<span data-ttu-id="98791-106">XML-файлы HelpInfo основаны на следующей схеме XML.</span><span class="sxs-lookup"><span data-stu-id="98791-106">HelpInfo XML files are based on the following XML schema.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="http://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
  <element name="HelpInfo">
    <complexType>
      <sequence>
        <element name="HelpContentURI" type="anyURI" minOccurs="1" maxOccurs="1" />
        <element name="SupportedUICultures" minOccurs="1" maxOccurs="1">
          <complexType>
            <sequence>
              <element name="UICulture" minOccurs="1" maxOccurs="unbounded">
                <complexType>
                  <sequence>
                    <element name="UICultureName" type="language" minOccurs="1" maxOccurs="1" />
                    <element name="UICultureVersion" type="string" minOccurs="1" maxOccurs="1" />
                  </sequence>
                </complexType>
              </element>
            </sequence>
          </complexType>
        </element>
      </sequence>
    </complexType>
  </element>
</schema>
```

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="98791-107">HelpInfo XML-элементы</span><span class="sxs-lookup"><span data-stu-id="98791-107">HelpInfo XML Elements</span></span>

<span data-ttu-id="98791-108">XML-файл HelpInfo содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="98791-108">The HelpInfo XML file includes the following elements.</span></span>

- <span data-ttu-id="98791-109">**Хелпконтентури** — содержит универсальный код ресурса (URI) расположения CAB-файлов справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="98791-109">**HelpContentURI** - Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="98791-110">URI должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="98791-110">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="98791-111">URI должен указывать расположение в Интернете, но не должно включать имя CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="98791-111">The URI should specify an internet location, but must not include the CAB filename.</span></span> <span data-ttu-id="98791-112">Значение **хелпконтентури** может быть таким же или отличным от значения **HelpInfoURI** .</span><span class="sxs-lookup"><span data-stu-id="98791-112">The **HelpContentURI** value can be the same or different from the **HelpInfoURI** value.</span></span>

- <span data-ttu-id="98791-113">**Суппортедуикултурес** — представляет файлы справки модуля во всех культурах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98791-113">**SupportedUICultures** - Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="98791-114">Содержит элементы **UICulture** , каждый из которых представляет набор файлов справки для модуля в указанном языке и региональных ПАРАМЕТРАХ пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98791-114">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

- <span data-ttu-id="98791-115">**UICulture** — представляет набор файлов справки для модуля в заданном языке и региональных ПАРАМЕТРАХ пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98791-115">**UICulture** - Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="98791-116">Добавьте элемент **UICulture** для каждого языка и региональных параметров пользовательского интерфейса, в которых записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="98791-116">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

- <span data-ttu-id="98791-117">**Уикултуренаме** — содержит код языка для языка и региональных параметров пользовательского интерфейса, в который записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="98791-117">**UICultureName** - Contains the language code for the UI culture in which the help files are written.</span></span>

- <span data-ttu-id="98791-118">**Уикултуреверсион** — содержит номер версии из 4 частей в "N1. N2. N3. N4 "формат, представляющий версию CAB-файла справки в культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98791-118">**UICultureVersion** - Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="98791-119">Увеличивайте этот номер версии при передаче новых CAB-файлов справки в язык и региональные параметры пользовательского интерфейса, заданные параметром **уикултуренаме**.</span><span class="sxs-lookup"><span data-stu-id="98791-119">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="98791-120">Дополнительные сведения об этом значении см. в разделе [класс версии](/dotnet/api/system.version).</span><span class="sxs-lookup"><span data-stu-id="98791-120">For more information about this value, see [Version Class](/dotnet/api/system.version).</span></span>
