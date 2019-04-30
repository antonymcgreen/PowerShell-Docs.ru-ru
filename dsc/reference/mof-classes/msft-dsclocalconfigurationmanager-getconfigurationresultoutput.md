---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: ea572a4a66befd4e4b8d83e2957632b1b5ed7d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078651"
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a>Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager

Получает выходные данные агента конфигурации, относящиеся к определенному заданию.

## <a name="syntax"></a>Синтаксис

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a>Параметры

*jobId* \[in\] Идентификатор задания, для которого необходимо получить выходные данные.

*resumeOutputBookmark* \[in\] Указывает, что выходные данные должны быть продолжением от предыдущей закладки.

*output* \[out\] Выходные данные для указанного задания.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Замечания

Это статический метод.

## <a name="requirements"></a>Требования

**MOF-файл:** DscCore.mof

**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>См. также:

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)