---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 4956900ecd2c9cb7f2e2b5bcab94616f9f5d5565
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682807"
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод RollBack класса MSFT_DSCLocalConfigurationManager

Выполняет откат конфигурации к предыдущей версии.

## <a name="syntax"></a>Синтаксис

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a>Параметры

*configurationNumber* \[in\] Указывает запрошенную конфигурацию.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)