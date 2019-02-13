---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 03555cc73da1272bdebebc3d93b26aaf8fabc18e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55679690"
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager

Удаляет файлы конфигурации.

## <a name="syntax"></a>Синтаксис

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>Параметры

*Stage* \[in\] Указывает, какой документ конфигурации необходимо удалить. Допустимы следующие значения:

|Значение |Описание |
|:--- |:---|
|**1** | Документ **текущей** конфигурации (current.mof). |
|**2** | Документ **ожидающей** конфигурации (pending.mof).  |
|**4** | Документ **предыдущей** конфигурации (previous.mof). |

*Force* \[in\] **true** для принудительного удаления конфигурации.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)