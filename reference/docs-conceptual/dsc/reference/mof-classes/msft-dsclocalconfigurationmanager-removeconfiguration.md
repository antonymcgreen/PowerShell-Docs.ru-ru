---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration
ms.openlocfilehash: ef15c873d8dfaf28e5cdeb611b72a70921c099be
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464355"
---
# <a name="removeconfiguration-method"></a>Метод RemoveConfiguration

Удаляет файлы конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>Параметры

**Stage** \[in\] Указывает, какой документ конфигурации необходимо удалить. Допустимы следующие значения:

|Значение |Описание |
|:--- |:---|
|**1** | Документ **текущей** конфигурации (current.mof). |
|**2** | Документ **ожидающей** конфигурации (pending.mof).  |
|**4** | Документ **предыдущей** конфигурации (previous.mof). |

*Force* \[in\] **true** для принудительного удаления конфигурации.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также раздел

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
