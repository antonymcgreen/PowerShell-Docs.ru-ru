---
title: Наборы параметров командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: dfe747893b4aef6376ea3b12dd79b7c144455ed0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415685"
---
# <a name="cmdlet-parameter-sets"></a>Наборы параметров командлета

В PowerShell используются наборы параметров, позволяющие создавать один командлет, который может выполнять различные действия в различных сценариях. Наборы параметров позволяют предоставлять пользователю различные параметры. И, чтобы получить различные сведения на основе параметров, указанных пользователем.

## <a name="examples-of-parameter-sets"></a>Примеры наборов параметров

Например, командлет PowerShell `Get-EventLog` возвращает различные сведения в зависимости от того, указан ли пользователь в списке **или** параметре типа " **список** ". Если указан параметр **List** , командлет возвращает сведения о самих файлах журнала, но не сведения о событиях, которые они содержат. Если указан параметр " **/l** ", командлет возвращает сведения о событиях в определенном журнале событий. Параметры **List** и параметров задания указывают два отдельных набора параметров.

## <a name="unique-parameter"></a>Уникальный параметр

Каждый набор параметров должен иметь уникальный параметр, используемый средой выполнения PowerShell для предоставления соответствующего набора параметров. Если это возможно, уникальный параметр должен быть обязательным. Если параметр является обязательным, пользователь должен указать параметр, а среда выполнения PowerShell использует этот параметр для определения набора параметров. Уникальный параметр не может быть обязательным, если командлет предназначен для запуска без указания каких-либо параметров.

## <a name="multiple-parameter-sets"></a>Несколько наборов параметров

На следующем рисунке в левом столбце показаны три допустимых набора параметров. **Параметр A** уникален для первого набора параметров, **параметр B** уникален для второго набора параметров, а **параметр C** является уникальным для третьего набора параметров. В правом столбце наборы параметров не имеют уникального параметра.

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a>Требования к наборам параметров

Следующие требования применяются ко всем наборам параметров.

- Каждый набор параметров должен иметь по крайней мере один уникальный параметр. Если это возможно, присвоить этому параметру обязательный параметр.

- Набор параметров, содержащий несколько позиционированных параметров, должен определять уникальные позиции для каждого параметра. Ни один из двух параметров позиционирования не может указывать одну и ту же точку.

- Только один параметр в наборе может объявить ключевое слово `ValueFromPipeline` со значением `true`.
  Несколько параметров могут определять ключевое слово `ValueFromPipelineByPropertyName` со значением `true`.

- Если для параметра не задан набор параметров, параметр относится ко всем наборам параметров.

> [!NOTE]
> Для командлета или функции существует ограничение в 32 наборов параметров.

## <a name="default-parameter-sets"></a>Наборы параметров по умолчанию

Если определено несколько наборов параметров, можно использовать ключевое слово `DefaultParameterSetName` атрибута **командлета** , чтобы указать набор параметров по умолчанию. PowerShell использует набор параметров по умолчанию, если не может определить набор параметров для использования на основе сведений, предоставленных командой. Дополнительные сведения об атрибуте **командлета** см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).

## <a name="declaring-parameter-sets"></a>Объявление наборов параметров

Чтобы создать набор параметров, необходимо указать ключевое слово `ParameterSetName` при объявлении атрибута **Parameter** для каждого параметра в наборе параметров. Для параметров, принадлежащих к нескольким наборам параметров, добавьте атрибут **параметра** для каждого набора параметров. Этот атрибут позволяет определить параметр по-разному для каждого набора параметров. Например, можно определить параметр как обязательный в одном наборе и необязательный в другом. Однако каждый набор параметров должен содержать один уникальный параметр. Дополнительные сведения см. в разделе [объявление атрибута Parameter](parameter-attribute-declaration.md).

В следующем примере параметр **username** является уникальным параметром набора параметров `Test01`, а параметр **ComputerName** является уникальным параметром набора параметров `Test02`. Параметр **шаредпарам** относится к обоим наборам и является обязательным для набора параметров `Test01`, но необязателен для набора параметров `Test02`.

```csharp
[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test02")]
public string ComputerName
{
  get { return computerName; }
  set { computerName = value; }
}
private string computerName;

[Parameter(Mandatory= true, ParameterSetName = "Test01")]
[Parameter(ParameterSetName = "Test02")]
public string SharedParam
{
    get { return sharedParam; }
    set { sharedParam = value; }
}
private string sharedParam;
```