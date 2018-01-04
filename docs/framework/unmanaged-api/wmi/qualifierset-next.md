---
title: "QualifierSet_Next 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_Next 함수에는 다음 한정자는 열거형에는 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01a9c9d162039547849597aaa9c8a6fa38a31455
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next 함수
다음 한정자에 대 한 호출을 시작 하는 열거형에는 검색 된 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`   
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`   
[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.

`lFlags`   
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pstrName`   
[out] 한정자의 이름입니다. 경우 `null`,이 매개 변수는 무시 되 고, 그렇지 않으면 `pstrName` 해야을 유효한이 가리키지 `BSTR` 또는 메모리 누수가 발생 합니다. Null이 아닌 함수는 항상 할당 하는 새 `BSTR` 반환 될 때 `WBEM_S_NO_ERROR`합니다.

`pVal`   
[out] 성공 하면 한정자의 값입니다. 함수가 실패 하면는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다. 이 매개 변수가 `null`, 매개 변수는 무시 됩니다.

`plFlavor`   
[out] 한정자 버전을 수신 하는 LONG에 대 한 포인터입니다. 버전 정보는 원하지 않을 경우이 매개 변수 수 `null`합니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 호출자에 게 로드 하지 않는 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)합니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 많은 한정자가 남아 있습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) 메서드.

호출 하 여 `QualifierSet_Next` 반복 함수 반환 될 때까지 모든 한정자를 열거 하는 함수 `WBEM_S_NO_MORE_DATA`합니다. 열거형을 조기에 종료를 호출 하는 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수입니다.

열거 동안 반환 되는 한정자의 순서는 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
