---
title: Delete 함수 (관리 되지 않는 API 참조)
description: Delete 함수는 CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7fcf5cff9f95b06a834d73df4090bd1edfca61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="delete-function"></a>Delete 함수
CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszName`  
[in] 삭제할 속성의 이름입니다. `wszName` 유효한 포인터 여야 합니다. `LPCWSTR`합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | 속성을 삭제할 수 없습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszzName`이 잘못되었습니다. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 속성이 존재 하지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | 속성은 기본 클래스에서 상속 됩니다. |
| `WBEM_E_SYSTEM_PROPERTY` | | 속성은 시스템 속성입니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | 함수는 현재 클래스에 대 한 재정의 기본값을 삭제 합니다. 부모 클래스에서이 속성에 대 한 기본값 reactiviated 되었습니다. | 

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
