---
title: Схема XML-файла HelpInfo
ms.date: 09/12/2016
ms.openlocfilehash: e894c1f2695ddbc5a386f8fec96054a7b31e7778
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893260"
---
# <a name="helpinfo-xml-schema"></a>Схема XML-файла HelpInfo

В этом разделе содержится схема XML для обновляемых файлов справки, которые обычно называются «HelpInfo XML Files».

## <a name="helpinfo-xml-schema"></a>Схема XML-файла HelpInfo

XML-файлы HelpInfo основаны на следующей схеме XML.

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="https://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
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

## <a name="helpinfo-xml-elements"></a>HelpInfo XML-элементы

XML-файл HelpInfo содержит следующие элементы.

- **Хелпконтентури** — содержит универсальный код ресурса (URI) расположения CAB-файлов справки для модуля. URI должен начинаться с "http" или "HTTPS". URI должен указывать расположение в Интернете, но не должно включать имя CAB-файла. Значение **хелпконтентури** может быть таким же или отличным от значения **HelpInfoURI** .

- **Суппортедуикултурес** — представляет файлы справки модуля во всех культурах пользовательского интерфейса. Содержит элементы **UICulture** , каждый из которых представляет набор файлов справки для модуля в указанном языке и региональных ПАРАМЕТРАХ пользовательского интерфейса.

- **UICulture** — представляет набор файлов справки для модуля в заданном языке и региональных ПАРАМЕТРАХ пользовательского интерфейса. Добавьте элемент **UICulture** для каждого языка и региональных параметров пользовательского интерфейса, в которых записываются файлы справки.

- **Уикултуренаме** — содержит код языка для языка и региональных параметров пользовательского интерфейса, в который записываются файлы справки.

- **Уикултуреверсион** — содержит номер версии из 4 частей в "N1. N2. N3. N4 "формат, представляющий версию CAB-файла справки в культуре пользовательского интерфейса. Увеличивайте этот номер версии при передаче новых CAB-файлов справки в язык и региональные параметры пользовательского интерфейса, заданные параметром **уикултуренаме**. Дополнительные сведения об этом значении см. в разделе [класс версии](/dotnet/api/system.version).
