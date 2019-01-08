---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод PerformRequiredConfigurationChecks класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b92eefb7fbea6d96afa31f6b802ba10fe20d4103
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047903"
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод PerformRequiredConfigurationChecks класса MSFT_DSCLocalConfigurationManager

Запускает проверку согласованности с помощью планировщика заданий.

## <a name="syntax"></a>Синтаксис

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>Параметры

*Flags* \[in\] Битовая маска, определяющая тип выполняемой проверки согласованности. Допустимы следующие значения, которые можно объединить с помощью битовой операции **OR**:

|Значение |Описание |
|:--- |:---|
|**1** | Обычная проверка согласованности. |
|**2** | Продолжение проверки согласованности после перезагрузки. Это значение не следует использовать в сочетании с другими значениями. |
|**4** | Конфигурация должна извлекаться с запрашивающего сервера, указанного в метаконфигурации для узла. Это значение следует всегда использовать в сочетании с **1**, если указано значение **5**. |
|**8** | Состояние отправки на сервер отчетов. |

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

MOF** DscCore.mof

-Namespace Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)