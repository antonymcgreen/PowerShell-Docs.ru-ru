---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод PerformRequiredConfigurationChecks
ms.openlocfilehash: ea4294ffdcb2580fa7b39b18966b642d58073eb6
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464457"
---
# <a name="performrequiredconfigurationchecks-method"></a>Метод PerformRequiredConfigurationChecks

Запускает проверку согласованности с помощью планировщика заданий.

## <a name="syntax"></a>Синтаксис

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>Параметры

**Flags** \[in\] Битовая маска, определяющая тип выполняемой проверки согласованности. Допустимы следующие значения, которые можно объединить с помощью битовой операции **OR**:

|Значение |Описание |
|:--- |:---|
|**1** | Обычная проверка согласованности. |
|**2** | Продолжение проверки согласованности после перезагрузки. Это значение не следует использовать в сочетании с другими значениями. |
|**4** | Конфигурация должна извлекаться с запрашивающего сервера, указанного в метаконфигурации для узла. Это значение следует всегда использовать в сочетании с **1**, если указано значение **5**. |
|**8** | Состояние отправки на сервер отчетов. |

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
