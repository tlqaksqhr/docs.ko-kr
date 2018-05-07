---
title: GetMethodQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetMethodQualifierSet 함수 메서드의 한정자 집합을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b1f73e999738fbb59342aeab391132ac454c8dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="getmethodqualifierset-function"></a>GetMethodQualifierSet 함수
특정 방법에 대해 설정할 한정자를 검색 합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszMethod`  
[in] 메서드 이름입니다. `wszMethod` 유효한 가리켜야 `LPCWSTR`합니다. 

`ppQualSet`  
[out] 메서드의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다. `ppQualSet`가 `null`이 될 수 없는 경우 오류가 발생 하는 경우 새 개체가 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`합니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 메서드는 존재 하지 않습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수는 `null`합니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) 메서드. 

이 함수에 대 한 호출에는 현재 개체는 CIM 클래스 정의 하는 경우에 지원 됩니다. 조작 메서드를 사용할 수 없기 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 ponters 합니다.

각 메서드에 자체 한정자 있을 수 있으므로 [IWbemQualifierSet 포인터](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 호출자 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
