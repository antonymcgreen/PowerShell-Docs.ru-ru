---
title: Схемы HelpInfo XML | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74dcb396-c295-4457-b84c-4432bdaa8df3
caps.latest.revision: 7
ms.openlocfilehash: 0f965f4ee1ef92a6a538b52b4348c04366cabf66
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862320"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="1ba89-102">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="1ba89-102">HelpInfo XML Schema</span></span>

<span data-ttu-id="1ba89-103">Этот раздел содержит схемы XML для файлов обновляемые сведения, Справка, известную как «HelpInfo XML files».</span><span class="sxs-lookup"><span data-stu-id="1ba89-103">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="1ba89-104">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="1ba89-104">HelpInfo XML Schema</span></span>

<span data-ttu-id="1ba89-105">Файлы HelpInfo XML основаны на следующей схеме XML.</span><span class="sxs-lookup"><span data-stu-id="1ba89-105">HelpInfo XML files are based on the following XML schema.</span></span>

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

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="1ba89-106">HelpInfo XML-элементов</span><span class="sxs-lookup"><span data-stu-id="1ba89-106">HelpInfo XML Elements</span></span>

<span data-ttu-id="1ba89-107">XML-файл HelpInfo включает следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="1ba89-107">The HelpInfo XML file includes the following elements.</span></span>

<span data-ttu-id="1ba89-108">HelpContentURI содержит URI расположения CAB-файлы для модуля справки.</span><span class="sxs-lookup"><span data-stu-id="1ba89-108">HelpContentURI Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="1ba89-109">URI должен начинаться с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="1ba89-109">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="1ba89-110">URI должен указывать расположение Internet, но не должен включать имя CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="1ba89-110">The URI should specify an Internet location, but must not include the CAB file name.</span></span> <span data-ttu-id="1ba89-111">**HelpContentURI** значения могут совпадать или отличаться от **HelpInfoURI** значение.</span><span class="sxs-lookup"><span data-stu-id="1ba89-111">The **HelpContentURI** value can be the  same or different from the **HelpInfoURI** value.</span></span>

<span data-ttu-id="1ba89-112">Представляет SupportedUICultures файлы справки модуля на все языки и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1ba89-112">SupportedUICultures Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="1ba89-113">Содержит **UICulture** элементов, каждый из которых представляет набор файлов справки для модуля в указанный язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1ba89-113">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

<span data-ttu-id="1ba89-114">UICulture представляет набор файлов справки для модуля в указанный язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1ba89-114">UICulture Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="1ba89-115">Добавить **UICulture** элемент для каждого языка пользовательского интерфейса, в который записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="1ba89-115">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

<span data-ttu-id="1ba89-116">Contains UICultureName код языка для языка пользовательского интерфейса, в который записываются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="1ba89-116">UICultureName Contains the language code for the UI culture in which the help files are written.</span></span>

<span data-ttu-id="1ba89-117">UICultureVersion содержит номер версии 4 частей в «N1. N2. N3. N4» формат, который представляет версию файла справки CAB-файла в язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1ba89-117">UICultureVersion Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="1ba89-118">Этот номер версии увеличивается при каждой отправке нового справки CAB-файлов в язык и региональные параметры пользовательского интерфейса, определяемый **UICultureName**.</span><span class="sxs-lookup"><span data-stu-id="1ba89-118">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="1ba89-119">Дополнительные сведения об этом значении см. в разделе «Версии класса (система)» на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="1ba89-119">For more information about this value, see "Version Class (System)" in MSDN.</span></span>