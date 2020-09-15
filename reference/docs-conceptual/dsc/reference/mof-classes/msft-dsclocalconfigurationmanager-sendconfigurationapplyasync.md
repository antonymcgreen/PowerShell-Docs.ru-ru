---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfigurationApplyAsync
ms.openlocfilehash: 4cfac5edb5fed94ee69deb98d7aa6be56b51c5b3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463743"
---
# <a name="sendconfigurationapplyasync-method"></a>Метод SendConfigurationApplyAsync

Асинхронно отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a>Параметры

**ConfigurationData** \[in\] Данные среды для конфигурации.

**force** \[in\] **true** Принудительная остановка конфигурации.

**jobId** \[in\] Идентификатор задания, для которого отправляется конфигурация.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
