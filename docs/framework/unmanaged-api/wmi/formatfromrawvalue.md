---
title: FormatFromRawValue 함수 (관리 되지 않는 API 참조)
description: FormatFromRawValue 함수 원시 성능 데이터를 지정된 된 형식으로 변환합니다.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0710b26237b350f1dfbc7d2464b7a131373604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue 함수
시간 기반 형식 변환 되 면 지정된 된 형식으로 원시 성능 데이터 값을 하나 또는 두 개의 원시 성능 데이터 값으로 변환 합니다.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a>매개 변수

`dwCounterType`  
[in] 카운터 형식입니다. 목록이 카운터 형식에 대 한 참조 [WMI 성능 카운터 형식](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx)합니다. `dwCounterType` 임의의 형식일 수 있습니다 카운터를 제외 하 고 `PERF_LARGE_RAW_FRACTION` 및 `PERF_LARGE_RAW_BASE`합니다. 

`dwFormat`  
[in] 원시 성능 데이터를 변환할 대상 형식입니다. 다음 값 중 하나일 수 있습니다.

|상수  |값  |설명 |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | 배정밀도 부동 소수점 값으로 계산된 된 값을 반환 합니다. | 
| `PDH_FMT_LARGE` | 0x00000400 | 64 비트 정수로 계산된 된 값을 반환 합니다. |
| `PDH_FMT_LONG` | 0x00000100 | 32 비트 정수로 계산된 된 값을 반환 합니다. |

이전 값 중 하나 ORed 다음 배율 플래그 중 하나가 될 수 있습니다.

|상수  |값  |설명 |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | 카운터의 배율 인수는 적용 되지 않습니다. |
| `PDH_FMT_1000` | 0x00002000 | 1, 000 최종 값을 곱하십시오. | 

`pTimeBase`  
[in] 형식 변환에 필요한 경우 시간 기준에 대 한 포인터입니다. 시간 기준 정보가 형식 변환에 대 한 필요가 없는 경우이 매개 변수 값은 무시 됩니다.

`pRawValue1` [in] 에 대 한 포인터는 [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) 원시 성능 값을 나타내는 구조입니다.

`pRawValue2` [in] 에 대 한 포인터는 [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) 구조를 두 번째 원시 성능 값을 나타냅니다. 두 번째 원시 성능 값 필요가 없는 경우이 매개 변수 여야 합니다 `null`합니다.

`pFmtValue` [out] 에 대 한 포인터는 [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) 구조체 형식이 지정 된 성능 값입니다.

## <a name="return-value"></a>반환 값

다음 값이이 함수에 의해 반환 됩니다.

|상수  |값  |설명  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | 함수 호출은 성공 합니다. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | 필요한 인수가 없거나 잘못 되었습니다. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | 핸들이 올바른 PDH 개체가 아닙니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **라이브러리:** PerfCounter.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
