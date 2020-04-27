---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953361"
---
# <a name="stopconfiguration-method"></a>Метод StopConfiguration

Останавливает выполняемое изменение конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>Параметры

*force* \[in\] **true** Принудительная остановка конфигурации.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
