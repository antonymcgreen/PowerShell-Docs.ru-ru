---
title: Пример XML-файла HelpInfo
ms.date: 09/12/2016
ms.openlocfilehash: ec9a2a1afed4f22be00900cbc80b580ff99f8f38
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86953273"
---
# <a name="helpinfo-xml-sample-file"></a>Пример XML-файла HelpInfo

В этом разделе представлен пример правильно сформированного файла справочной информации с правильным форматом, который обычно называется XML-файлом HelpInfo. В этом примере файла элементы языка и региональных параметров пользовательского интерфейса упорядочиваются в алфавитном порядке по имени языка и региональных параметров пользовательского интерфейса. Рекомендуется использовать алфавитный порядок, но это не обязательно.

## <a name="helpinfo-xml-sample-file"></a>Пример XML-файла HelpInfo

```xml

<?xml version="1.0" encoding="utf-8"?>
<HelpInfo xmlns="http://schemas.microsoft.com/powershell/help/2010/05">
   <HelpContentURI>https://go.microsoft.com/fwlink/?LinkID=141553</HelpContentURI>
   <SupportedUICultures>
    <UICulture>
      <UICultureName>de-DE</UICultureName>
      <UICultureVersion>2.15.0.10</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>en-US</UICultureName>
      <UICultureVersion>3.2.0.7</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>it-IT</UICultureName>
      <UICultureVersion>1.1.0.5</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>ja-JP</UICultureName>
      <UICultureVersion>3.2.0.4</UICultureVersion>
    </UICulture>
   </SupportedUICultures>
</HelpInfo>

```
