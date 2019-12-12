---
title: HelpInfo XML-схема | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74dcb396-c295-4457-b84c-4432bdaa8df3
caps.latest.revision: 7
ms.openlocfilehash: 0f965f4ee1ef92a6a538b52b4348c04366cabf66
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360743"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="a149d-102">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="a149d-102">HelpInfo XML Schema</span></span>

<span data-ttu-id="a149d-103">В этом разделе содержится схема XML для обновляемых файлов справки, которые обычно называются «HelpInfo XML Files».</span><span class="sxs-lookup"><span data-stu-id="a149d-103">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="a149d-104">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="a149d-104">HelpInfo XML Schema</span></span>

<span data-ttu-id="a149d-105">XML-файлы HelpInfo основаны на следующей схеме XML.</span><span class="sxs-lookup"><span data-stu-id="a149d-105">HelpInfo XML files are based on the following XML schema.</span></span>

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

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="a149d-106">HelpInfo XML-элементы</span><span class="sxs-lookup"><span data-stu-id="a149d-106">HelpInfo XML Elements</span></span>

<span data-ttu-id="a149d-107">XML-файл HelpInfo содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="a149d-107">The HelpInfo XML file includes the following elements.</span></span>

<span data-ttu-id="a149d-108">Хелпконтентури содержит универсальный код ресурса (URI) расположения файлов справки CAB для модуля.</span><span class="sxs-lookup"><span data-stu-id="a149d-108">HelpContentURI Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="a149d-109">URI должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="a149d-109">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="a149d-110">URI должен указывать расположение в Интернете, но не должно включать имя CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="a149d-110">The URI should specify an Internet location, but must not include the CAB file name.</span></span> <span data-ttu-id="a149d-111">Значение **хелпконтентури** может быть таким же или отличным от значения **HelpInfoURI** .</span><span class="sxs-lookup"><span data-stu-id="a149d-111">The **HelpContentURI** value can be the  same or different from the **HelpInfoURI** value.</span></span>

<span data-ttu-id="a149d-112">Суппортедуикултурес представляет файлы справки модуля во всех культурах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a149d-112">SupportedUICultures Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="a149d-113">Содержит элементы **UICulture** , каждый из которых представляет набор файлов справки для модуля в указанном языке и региональных ПАРАМЕТРАХ пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a149d-113">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

<span data-ttu-id="a149d-114">UICulture представляет набор файлов справки для модуля в заданном языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a149d-114">UICulture Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="a149d-115">Добавьте элемент **UICulture** для каждого языка и региональных параметров пользовательского интерфейса, в которых записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="a149d-115">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

<span data-ttu-id="a149d-116">Уикултуренаме содержит код языка для языка и региональных параметров пользовательского интерфейса, в который записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="a149d-116">UICultureName Contains the language code for the UI culture in which the help files are written.</span></span>

<span data-ttu-id="a149d-117">Уикултуреверсион содержит номер версии из 4 частей в "N1. N2. N3. N4 "формат, представляющий версию CAB-файла справки в культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a149d-117">UICultureVersion Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="a149d-118">Увеличивайте этот номер версии при передаче новых CAB-файлов справки в язык и региональные параметры пользовательского интерфейса, заданные параметром **уикултуренаме**.</span><span class="sxs-lookup"><span data-stu-id="a149d-118">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="a149d-119">Дополнительные сведения об этом значении см. в разделе "класс версии (System)" в MSDN.</span><span class="sxs-lookup"><span data-stu-id="a149d-119">For more information about this value, see "Version Class (System)" in MSDN.</span></span>