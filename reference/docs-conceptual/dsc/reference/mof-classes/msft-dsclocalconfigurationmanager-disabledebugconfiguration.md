---
ms.date: 07/14/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод DisableDebugConfiguration
ms.openlocfilehash: 52d55ff6b1fd126482bbaa9480efc131ab2f100c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463760"
---
# <a name="disabledebugconfiguration-method"></a>Метод DisableDebugConfiguration

Отключает отладку ресурсов DSC.

## <a name="syntax"></a>Синтаксис

```mof
uint32 DisableDebugConfiguration();
```

## <a name="parameters"></a>Параметры

Этот метод не имеет параметров.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
