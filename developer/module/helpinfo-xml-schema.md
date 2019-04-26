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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082470"
---
# <a name="helpinfo-xml-schema"></a>Схема XML-файла HelpInfo

Этот раздел содержит схемы XML для файлов обновляемые сведения, Справка, известную как «HelpInfo XML files».

## <a name="helpinfo-xml-schema"></a>Схема XML-файла HelpInfo

Файлы HelpInfo XML основаны на следующей схеме XML.

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

## <a name="helpinfo-xml-elements"></a>HelpInfo XML-элементов

XML-файл HelpInfo включает следующие элементы.

HelpContentURI содержит URI расположения CAB-файлы для модуля справки. URI должен начинаться с «http» или «https». URI должен указывать расположение Internet, но не должен включать имя CAB-файла. **HelpContentURI** значения могут совпадать или отличаться от **HelpInfoURI** значение.

Представляет SupportedUICultures файлы справки модуля на все языки и региональные параметры пользовательского интерфейса. Содержит **UICulture** элементов, каждый из которых представляет набор файлов справки для модуля в указанный язык и региональные параметры пользовательского интерфейса.

UICulture представляет набор файлов справки для модуля в указанный язык и региональные параметры пользовательского интерфейса. Добавить **UICulture** элемент для каждого языка пользовательского интерфейса, в который записываются файлы справки.

Contains UICultureName код языка для языка пользовательского интерфейса, в который записываются файлы справки.

UICultureVersion содержит номер версии 4 частей в «N1. N2. N3. N4» формат, который представляет версию файла справки CAB-файла в язык и региональные параметры пользовательского интерфейса. Этот номер версии увеличивается при каждой отправке нового справки CAB-файлов в язык и региональные параметры пользовательского интерфейса, определяемый **UICultureName**. Дополнительные сведения об этом значении см. в разделе «Версии класса (система)» на сайте MSDN.